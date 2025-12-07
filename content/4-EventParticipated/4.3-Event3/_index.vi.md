---
title: "Event 3"
date: 2025-09-10
weight: 3
chapter: false
pre: " <b> 4.3. </b> "
---


# Bài thu hoạch “Reinventing DevSecOps”

### Mục Đích Của Sự Kiện

- Định nghĩa lại quy trình phát triển phần mềm an toàn (DevSecOps Lifecycle) từ khâu lập kế hoạch đến vận hành.
- Giới thiệu bộ công cụ (Toolchain) toàn diện để tích hợp bảo mật vào từng giai đoạn của CI/CD.
- Xây dựng tư duy "Security-First" cho đội ngũ phát triển và vận hành.

### Đơn Vị Tổ Chức

- **CMC Global**

### Nội Dung Nổi Bật

#### 1. Vòng Đời DevSecOps (The DevSecOps Lifecycle)

Quy trình được chia thành 7 giai đoạn khép kín, đảm bảo bảo mật không phải là "nút thắt cổ chai" mà là một phần của dòng chảy:

1.  **PLAN (Lập kế hoạch):**
    - Xác định yêu cầu bảo mật ngay từ đầu (Security Requirements).
    - Thống nhất mục tiêu giữa Dev, Sec và Ops.
    - Xây dựng lộ trình bảo mật (Security Roadmap) bám sát mục tiêu dự án.
2.  **CODE (Viết mã):**
    - Áp dụng các tiêu chuẩn Clean Code và Secure Coding.
    - Sử dụng **SAST** (Static Application Security Testing) ngay trên IDE để phát hiện lỗi sớm.
    - Hình thành tư duy "Security-first" cho Developer.
3.  **BUILD (Xây dựng):**
    - Tự động kiểm tra bảo mật trong CI/CD Pipeline.
    - Quét các thư viện phụ thuộc (Dependency Scan) và mã nhị phân (Binary Scan).
    - Đảm bảo bản build an toàn và nhất quán (Immutable Artifacts).
4.  **TEST (Kiểm thử):**
    - Chạy quét lỗ hổng (Vulnerability Scan) và **DAST** (Dynamic Application Security Testing).
    - Thực hiện Penetration Test (Kiểm thử xâm nhập).
5.  **DEPLOY (Triển khai):**
    - Kiểm tra cấu hình và **IaC** (Infrastructure as Code) trước khi deploy.
    - Giám sát cấu hình Runtime.
6.  **OPERATE (Vận hành):**
    - Tự động vá lỗi (Auto-patching) và cập nhật bảo mật liên tục.
    - Có quy trình phản ứng sự cố (Incident Response).
7.  **MONITOR (Giám sát):**
    - Theo dõi liên tục các mối đe dọa (Threats).
    - Sử dụng Real-time Analytics và các công cụ cảnh báo (Alerting).

#### 2. Hệ Sinh Thái Công Cụ (DevSecOps Toolchain Overview)

Một hệ thống DevSecOps mạnh mẽ cần sự phối hợp của nhiều công cụ chuyên biệt:

- **Pre-commit & Code Quality:**
    - *SonarQube, Codacy*: Kiểm tra chất lượng code.
    - *GitLeaks*: Quét và ngăn chặn việc lộ Secret/Key trong code trước khi commit.
- **Dependency & SBOM Scanning:**
    - *Syft, Grype, Dependency-Track*: Quản lý các gói phần mềm và phát hiện lỗ hổng trong thư viện bên thứ 3.
- **IaC & Policy-as-Code:**
    - *Checkov, Tfsec*: Quét lỗi bảo mật trong file Terraform/Kubernetes.
    - *OPA Gatekeeper, Kyverno*: Thực thi chính sách tuân thủ tự động trên Cluster.
- **SAST / DAST & Security Tests:**
    - *Trivy, Checkmarx*: Phát hiện lỗ hổng toàn diện từ Code đến Runtime.
- **CI/CD Integration:**
    - *Jenkins, GitHub Actions, GitLab CI, ArgoCD*: Nền tảng để tự động hóa toàn bộ quy trình trên.
- **Monitoring & Logging:**
    - *Prometheus, Grafana, Loki*: Giám sát sức khỏe hệ thống (Observability).
- **Alerting & Governance:**
    - *Slack, Email, AI Anomaly Detection*: Cảnh báo tức thì khi có sự cố.

### Những Gì Học Được

#### Tư Duy "Shift Left"

- Bảo mật không nên để đến cuối mới làm (Giai đoạn Test/Operate) mà phải đưa sang trái (Shift Left) - tức là làm ngay từ khâu **Plan** và **Code**. Việc phát hiện lỗi sớm giúp tiết kiệm chi phí sửa chữa gấp nhiều lần.

#### Tầm Quan Trọng Của Automation

- Không thể làm bảo mật thủ công trong thời đại Cloud. Cần tích hợp các công cụ quét (Scan) vào Pipeline để chặn các bản build lỗi một cách tự động.

#### Quản Lý Rủi Ro Chuỗi Cung Ứng (Supply Chain Security)

- Thông qua việc quét Dependency (SBOM), ta có thể ngăn chặn các cuộc tấn công vào thư viện thứ 3 (tương tự vụ Log4j).

### Ứng Dụng Vào Công Việc

- **Tích hợp GitLeaks**: Cài đặt ngay pre-commit hook để ngăn chặn việc vô tình push AWS Access Key lên GitHub.
- **Triển khai SonarQube**: Tích hợp vào quy trình CI hiện tại để đo lường nợ kỹ thuật và lỗ hổng bảo mật.
- **Áp dụng IaC Scanning**: Sử dụng **Checkov** để quét các file CloudFormation/Terraform trước khi apply hạ tầng lên AWS.
- **Monitoring**: Thiết lập Dashboard Grafana để theo dõi trạng thái ứng dụng real-time.

### Trải nghiệm trong event

Mặc dù chỉ tham gia qua hình thức theo dõi tài liệu, nhưng nội dung của CMC Global mang lại cái nhìn rất hệ thống về DevSecOps.

#### Sự rõ ràng trong quy trình

- Slide về **DevSecOps Lifecycle** giúp mình hình dung rõ ràng bức tranh toàn cảnh, biết được ở mỗi giai đoạn cần làm gì thay vì chỉ tập trung vào viết code như trước đây.

#### Bộ công cụ thực chiến

- Slide **Toolchain** là một "kho báu" thực sự. Nó cung cấp danh sách các công cụ tiêu chuẩn ngành (Industry Standard) mà mình có thể tìm hiểu và áp dụng ngay lập tức cho dự án MiniMarket của mình (ví dụ như dùng Trivy để quét Docker Image).

  > Sự kiện đã nhấn mạnh rằng: Trong kỷ nguyên AI và Cloud, Bảo mật không phải là một tính năng (feature), mà là một văn hóa (culture) cần được xây dựng từ những dòng code đầu tiên.