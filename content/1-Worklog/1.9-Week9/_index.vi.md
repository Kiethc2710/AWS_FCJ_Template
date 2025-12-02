---
title: "Week 9 Worklog"
date: "2025-11-05"
weight: 1
chapter: false
pre: " <b> 1.9. </b> "
---

### Mục tiêu Tuần 9:

* Hiểu middleware và filter trong ASP.NET Core để xử lý request.
* Thực hiện luồng xác thực (Authentication) bằng Identity.
* Quản lý session người dùng và triển khai "Remember Me" bằng cookies.
* Thực hành đăng nhập / đăng xuất bảo mật.

### Nhiệm vụ cần thực hiện trong tuần:
| Ngày | Nhiệm vụ                                                                                                 | Ngày bắt đầu | Ngày hoàn thành | Tài liệu tham khảo         |
| ---- | -------------------------------------------------------------------------------------------------------- | ------------- | ---------------- | -------------------------- |
| 2    | - Nghiên cứu middleware & filter trong ASP.NET Core <br> - Tìm hiểu UseAuthentication() và UseAuthorization() | 03/11/2025    | 03/11/2025       | Microsoft Docs / Tutorials |
| 3    | - Triển khai chức năng Login và Logout bằng Identity                                                    | 04/11/2025    | 04/11/2025       | ASP.NET Core Identity Docs  |
| 4    | - Quản lý session cho người dùng đã đăng nhập <br> - Lưu thông tin user vào session                      | 05/11/2025    | 05/11/2025       | Tutorials / Sample Code     |
| 5    | - Triển khai "Remember Me" bằng cookies <br> - Tự động điền form login cho user quay lại                 | 06/11/2025    | 06/11/2025       | ASP.NET Core Cookie Docs    |
| 6    | - Kiểm tra toàn bộ luồng xác thực <br> - Đảm bảo các trang protected chỉ truy cập được khi đã đăng nhập | 07/11/2025    | 07/11/2025       | Kiểm tra code dự án         |

### Thành tựu Tuần 9:

* Hiểu và cấu hình thành công middleware và filter trong ASP.NET Core để xử lý request.
* Triển khai đăng nhập và đăng xuất bằng Identity, kèm quản lý session hợp lý.
* Thực hiện thành công chức năng "Remember Me" bằng cookies.
* Kiểm tra và xác nhận các trang bảo vệ chỉ truy cập được khi đã đăng nhập.
* Refactor code xác thực để đảm bảo bảo mật và dễ bảo trì hơn.
