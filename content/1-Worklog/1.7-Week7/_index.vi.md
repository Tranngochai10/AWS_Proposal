---
title: "Worklog Tuần 7"
date: 2025-09-09
weight: 7
chapter: false
pre: " <b> 1.7. </b> "
---

### Mục tiêu tuần 7:

* Bắt đầu dự án Web Quản lý Nhân viên - Phân tích yêu cầu và thiết kế hệ thống
* Nghiên cứu kiến trúc RBAC (Role-Based Access Control) và Authentication
* Thiết lập môi trường phát triển frontend
* Lên ý tưởng và wireframe cho trang Employee Login

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc                                                                                                                                    | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu                            |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------- | ------------ | --------------- | ----------------------------------------- |
| 1   | - Phân tích yêu cầu dự án Web Quản lý Nhân viên <br> - Nghiên cứu các tính năng: RBAC, Auth, Employee Profile, Payroll, Attendance         | 15/09/2025   | 15/09/2025      |                                          |
| 2   | - Nghiên cứu kiến trúc RBAC và các role: Admin HR, Manager, Employee, Payroll officer, Recruiter <br> - Tìm hiểu về MFA (2FA OTP/Authenticator) | 16/09/2025   | 16/09/2025      |                                          |
| 3   | - Thiết lập môi trường phát triển frontend (React/Vue/Angular) <br> - Cài đặt các thư viện cần thiết: UI framework, routing, state management | 17/09/2025   | 17/09/2025      |                                          |
| 4   | - Thiết kế wireframe và UI/UX cho trang Employee Login <br> - Xác định các phương thức đăng nhập: email/phone/SSO (Google, Microsoft) | 18/09/2025   | 18/09/2025      |                                          |
| 5   | - Lên kế hoạch chi tiết cho trang Employee Login <br> - Xác định các component cần thiết: LoginForm, SSO buttons, MFA input, Forgot password | 19/09/2025   | 19/09/2025      |                                          |
| 6   | - Review và hoàn thiện thiết kế <br> - Chuẩn bị tài nguyên: icons, images, color scheme cho login page                                    | 20/09/2025   | 20/09/2025      |                                          |

### Kết quả đạt được tuần 7:

* Đã phân tích và hiểu rõ yêu cầu của dự án Web Quản lý Nhân viên với các module chính:
  * **RBAC + Auth:** Login bằng email/phone/SSO, quản lý roles, MFA, Session management
  * **Employee Profile:** Quản lý hồ sơ nhân viên, hợp đồng, bảo hiểm, thuế
  * **Attendance & Time Tracking:** Chấm công, quản lý nghỉ phép
  * **Payroll:** Tính lương, phiếu lương, báo cáo
  * **Scheduling & Leave:** Lịch trình, đăng ký nghỉ phép
  * **Recruitment/ATS:** Tuyển dụng, quản lý ứng viên
  * **Training & Performance:** Đào tạo, đánh giá hiệu suất
  * **Reports & Dashboard:** Báo cáo và dashboard cho HR & CEO

* Nắm vững kiến trúc RBAC với các role:
  * **Admin HR:** Toàn quyền quản lý hệ thống
  * **Manager:** Quản lý nhân viên trong phòng ban
  * **Employee:** Nhân viên thông thường
  * **Payroll officer:** Quản lý lương thưởng
  * **Recruiter:** Tuyển dụng

* Đã thiết lập môi trường phát triển frontend thành công:
  * Cài đặt framework và các dependencies cần thiết
  * Cấu hình routing và state management
  * Thiết lập cấu trúc thư mục dự án

* Hoàn thành thiết kế wireframe và UI/UX cho trang Employee Login:
  * Giao diện đăng nhập với email/phone
  * Tích hợp SSO (Google, Microsoft)
  * Form nhập MFA/2FA
  * Link "Quên mật khẩu"
  * Responsive design cho mobile và desktop

* Xác định được các component cần phát triển:
  * LoginForm component
  * SSO authentication buttons
  * MFA/OTP input component
  * Forgot password modal
  * Session management logic
