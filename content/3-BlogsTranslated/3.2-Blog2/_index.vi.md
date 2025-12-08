---
title: "Blog 2"
date: "2025-09-10"
weight: 1
chapter: false
pre: " <b> 3.2. </b> "
---

# AWS Public Sector Blog  
## Xây dựng hệ thống y tế kiên cường thông qua điện toán đám mây (Cloud Computing)

**Tác giả:** Justin Bowden, Andrew Wiltshire, Senthil Gurumoorthi  
**Ngày:** 08 JUL 2025  
**Nguồn:** AWS Public Sector Blog  

---

# Tóm tắt

Khả năng phục hồi của hệ thống lâm sàng và vận hành trong chăm sóc sức khỏe không chỉ đơn thuần là vấn đề kỹ thuật mà còn là một ưu tiên chính sách quan trọng. Ngay cả những gián đoạn ngắn hạn đối với hồ sơ sức khỏe điện tử hoặc hệ thống lâm sàng cũng có thể ảnh hưởng trực tiếp đến việc chăm sóc và an toàn cho bệnh nhân.

AWS vừa phát hành hướng dẫn **“Chăm sóc sức khỏe linh hoạt thông qua điện toán đám mây: Hướng dẫn về chiến lược và chính sách”**, cung cấp khuôn khổ toàn diện nhằm nâng cao khả năng phục hồi trong hệ thống chăm sóc sức khỏe, đảm bảo tuân thủ pháp lý và cải thiện kết quả điều trị.

---

# Tại sao khả năng phục hồi đám mây lại quan trọng trong chăm sóc sức khỏe

Các tổ chức y tế hoạt động trong môi trường đặc thù, nơi **độ tin cậy của hệ thống ảnh hưởng trực tiếp đến sự an toàn bệnh nhân**.  
Sự phát triển của:

- Hồ sơ sức khỏe điện tử (EHR)
- Y tế từ xa (Telehealth)
- Thiết bị y tế kết nối (IoMT)

… tạo ra hệ sinh thái công nghệ phức tạp, đòi hỏi **hiệu suất cao, bảo mật mạnh và khả năng phục hồi vượt trội**.

Hướng dẫn AWS đưa ra các nguyên tắc then chốt:

- **Hệ thống phục hồi tự động** khi vượt ngưỡng lỗi  
- **Quy trình được xác thực thường xuyên** để đảm bảo phục hồi hiệu quả  
- **Kiến trúc phân tán**, tăng khả năng mở rộng, giảm điểm lỗi đơn (Single Point of Failure)

---

# Lợi thế của đám mây đối với chăm sóc sức khỏe

Hạ tầng đám mây AWS vượt trội hơn hạ tầng tại chỗ nhờ:

- Hệ thống **đa vùng (Regions)** và **nhiều vùng khả dụng (AZs)**
- Khả năng phân bổ khối lượng công việc tách biệt vật lý nhưng vẫn đảm bảo hiệu suất cao
- Tự động hóa bảo mật, hiệu suất và phục hồi thảm họa

Dưới đây là các ví dụ thực tế:

---

## **1. Tufts Medicine – Triển khai EHR Epic lên AWS trong 14 tháng**

- Di chuyển toàn bộ hệ thống EHR (sản xuất, DR, đào tạo) lên AWS  
- Hợp nhất công nghệ, hiện đại hóa ứng dụng  
- Trở thành hệ thống y tế **đầu tiên** chạy môi trường Epic đầy đủ trên AWS  
→ Kết quả: hiệu suất cao hơn, trải nghiệm tốt hơn cho bệnh nhân và nhân viên y tế.

---

## **2. Baptist Memorial Health Care (BMHC)**  
Duy trì dịch vụ cho **3 triệu bệnh nhân** tại 3 tiểu bang.

- Hợp tác với AWS Partner Optimum Healthcare IT  
- Di chuyển EHR lên AWS để khắc phục giới hạn hạ tầng cũ  
- Hiệu suất tăng **20%**  
- Chi phí sở hữu tổng thể giảm  
- Phục hồi thảm họa mạnh hơn trên **22 bệnh viện + 200 phòng khám**

---

## **3. NSW Health – Cải thiện hiệu suất gấp 10 lần**

- Ứng dụng hồ sơ bệnh nhân doanh nghiệp chạy nhanh hơn gấp **10 lần**  
- Giảm **70%** sự cố nghiêm trọng  
- Triển khai ứng dụng nhanh hơn **50%**  
- Môi trường được tạo mới từ 6–8 tuần → **chỉ còn < 4 giờ**  
- Lợi ích tài chính 16 triệu USD  
- Tiết kiệm **144.000 giờ làm việc** của bác sĩ tuyến đầu  
- Tích hợp:
  - AWS Security Hub  
  - Amazon GuardDuty  
→ Tự động kiểm tra bảo mật, phát hiện sớm mối đe dọa

---

# Xây dựng khuôn khổ phục hồi

Hướng dẫn đề xuất các bước:

- Xác định **khối lượng công việc quan trọng**  
- Thiết lập **RTO, RPO** hợp lý  
- Áp dụng mô hình **trách nhiệm chia sẻ**  
- Triển khai ứng dụng lên **nhiều vùng khả dụng (AZs)**  
- Xây dựng chiến lược phục hồi thảm họa toàn diện  
- Duy trì tuân thủ quy định y tế  

---

# Khuyến nghị chính sách cho lãnh đạo y tế

AWS đề xuất các nhà hoạch định chính sách:

- Thiết lập **chính sách ưu tiên đám mây**  
- Tạo **ưu đãi tài chính** thúc đẩy chuyển đổi số  
- Áp dụng **tiêu chuẩn quốc tế**  
- Tạo **khuôn khổ đánh giá khả năng phục hồi xuất sắc**  
- Xây dựng **chương trình đào tạo kỹ năng đám mây y tế**  
- Thiết lập **sandbox pháp lý** để thử nghiệm giải pháp mới  

---

# Bạn đã sẵn sàng tăng cường phục hồi hệ thống y tế?

Tải hướng dẫn đầy đủ:  
**“Chăm sóc Sức khỏe Phục hồi thông qua Điện toán Đám mây: Hướng dẫn Chiến lược và Chính sách”**

Hoặc liên hệ chuyên gia AWS để được tư vấn thêm.

---

# Giới thiệu tác giả

### **Justin Bowden**  
- Compliance & Security Assurance Principal – AWS  
- Hỗ trợ cơ quan ANZ tăng cường cloud resilience  
- Chuyên môn: risk management, security, operational resilience  

### **Andrew Wiltshire**  
- Head of Healthcare Public Policy – AWS APJ  
- 40 năm kinh nghiệm chăm sóc sức khỏe  
- Đam mê xe cổ và off-road  

### **Senthil Gurumoorthi**  
- Principal – AWS  
- Dẫn dắt các sáng kiến về data governance  
- Đồng tác giả ISPE GAMP 5 V2  
- Thành viên FDA-Industry CSA Team  
