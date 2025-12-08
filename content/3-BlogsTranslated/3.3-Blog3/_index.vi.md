---
title: "Blog 3"
date: "2025-09-10"
weight: 3
chapter: false
pre: " <b> 3.3. </b> "
---


#  Artificial Intelligence
## Xây dựng cơ sở kiến thức kịp thời với Amazon Bedrock

**Tác giả:** Steven Warwick  
**Ngày:** 07 JUL 2025  
**Nguồn:** Amazon Bedrock, Cơ sở kiến thức Amazon Bedrock, Tối ưu hóa chi phí đám mây, AI, SaaS  

---

# Tóm tắt

Các hệ thống SaaS đa thuê bao thường phải xử lý lượng lớn tài liệu, nhưng các phương pháp RAG truyền thống lại tiêu tốn tài nguyên do xử lý và lưu trữ nhúng cho cả những tài liệu không bao giờ được truy vấn.  

Kiến trúc **Just-in-time Knowledge Base** giúp giải quyết vấn đề này bằng cách:

- Chỉ xử lý tài liệu khi có nhu cầu (on-demand ingestion)  
- Tự động loại bỏ dữ liệu không còn sử dụng bằng **DynamoDB TTL**  
- Giảm chi phí OpenSearch Serverless  
- Hỗ trợ mô hình đa thuê bao với khả năng phân quyền, tách biệt dữ liệu mạnh mẽ  
- Cho phép định giá theo tầng (tier-based pricing) dựa trên cấu hình từng tenant  

Giải pháp này giúp các nhà cung cấp SaaS mở rộng quy mô linh hoạt, giảm tải vận hành và duy trì hiệu năng truy vấn cao.

---

# Tổng quan kiến trúc

Giải pháp sử dụng các dịch vụ chính:

- **Amazon Bedrock** – Xử lý tài liệu, truy vấn, tạo nội dung RAG  
- **Amazon OpenSearch Serverless** – Lưu trữ và truy vấn vectơ  
- **Amazon S3** – Lưu trữ tệp gốc  
- **Amazon DynamoDB** – Theo dõi metadata, TTL, tài liệu của từng tenant  
- **AWS Lambda** – Tự động dọn dẹp tài liệu đã hết hạn  
- **AWS CDK** – Triển khai kiến trúc hạ tầng  

Các thành phần phối hợp để đảm bảo chỉ tài liệu cần thiết mới được nhập vào cơ sở tri thức, còn tài liệu cũ sẽ tự động bị xóa.

---

# Quy trình hoạt động

## 1. Đăng nhập và gán tenant
Người dùng đăng nhập → hệ thống gán **tenantId** để xác định phạm vi dữ liệu và quyền truy cập.

## 2. Tạo dự án
Mỗi dự án chứa danh sách tệp mà người dùng muốn truy vấn.  
Hệ thống khởi tạo metadata liên kết **user – tenant – project**.

## 3. Tải tệp lên
Người dùng upload file qua URL ký trước.  
Hệ thống lưu file vào S3 và ghi metadata trong DynamoDB.

## 4. Ingest tài liệu theo yêu cầu (JIT ingestion)
Chỉ khi người dùng bắt đầu **chat với dự án**, các tệp mới được ingest vào Knowledge Base.

Mỗi tệp được gán **TTL theo gói dịch vụ của tenant**.

## 5. Làm mới TTL trong quá trình truy vấn
Tệp nào được truy vấn nhiều → TTL được gia hạn → tiếp tục tồn tại.  
Tài liệu không dùng → TTL hết hạn → tự động dọn dẹp.

## 6. Tự động xóa tài liệu
DynamoDB Streams phát hiện TTL hết hạn → Lambda xóa tài liệu khỏi Knowledge Base và OpenSearch.

---

# Ví dụ mã ingest tài liệu với TTL theo tenant

```python
# Ingesting files with tenant-specific TTL values
def ingest_files(user_id, tenant_id, project_id, files):
    tenants = json.loads(os.environ.get('TENANTS'))['Tenants']
    tenant = find_tenant(tenant_id, tenants)
    ttl = int(time.time()) + (int(tenant['FilesTTLHours']) * 3600)

    for file in files:
        file_id = file['id']
        s3_key = file.get('s3Key')
        bucket = file.get('bucket')

        knowledge_base_files_table.put_item(
            Item={
                'id': file_id,
                'userId': user_id,
                'tenantId': tenant_id,
                'projectId': project_id,
                'documentStatus': 'ready',
                'createdAt': int(time.time()),
                'ttl': ttl
            }
        )
