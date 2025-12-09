---
title: "Worklog Tuần 5"
date: 2025-09-09
weight: 5
chapter: false
pre: " <b> 1.5. </b> "
---
### Week 5 Objectives:
- Hiểu rõ mô hình trách nhiệm chia sẻ (Shared Responsibility Model)
- Nắm vững toàn bộ hệ thống IAM, bảo mật danh tính và quyền truy cập trên AWS
- Thành thạo các dịch vụ: IAM, Organizations, Identity Center, Cognito, KMS, Security Hub

### Tasks to be carried out this week:
| Day | Task                                                                                          | Start Date   | Completion Date | Reference Material                        |
| --- | --------------------------------------------------------------------------------------------- | ------------ | --------------- | ----------------------------------------- |
| 1–2 | Shared Responsibility Model + IAM căn bản (Root, IAM User, Group, Policy, Role, Principal)  | 25–26/08/2025| 26/08/2025      | https://cloudjourney.awsstudygroup.com/   |
| 3   | IAM Policy (Identity-based vs Resource-based), Evaluation Logic, Explicit Deny                | 27/08/2025   | 27/08/2025      |                                           |
| 4   | IAM Role, Trust Policy, STS, AssumeRole, Cross-account access, EC2 Instance Role             | 28/08/2025   | 28/08/2025      |                                           |
| 5   | AWS Organizations, OU, SCP, Consolidated Billing + AWS Identity Center + Permission Sets     | 29/08/2025   | 29/08/2025      |                                           |
| 6   | Amazon Cognito (User Pool vs Identity Pool), KMS (CMK, Data Key), Security Hub                    | 30/08/2025   | 30/08/2025      |                                           |

### Week 5 Achievements:

Hoàn thành xuất sắc toàn bộ nội dung tuần 5 với các kiến thức quan trọng sau:

- Hiểu sâu **Shared Responsibility Model**: AWS chịu trách nhiệm bảo mật hạ tầng đám mây (of the cloud), khách hàng chịu trách nhiệm bảo mật trong đám mây (in the cloud). Trách nhiệm thay đổi theo loại dịch vụ (IaaS → PaaS → SaaS).
- Bảo vệ tài khoản **Root User** theo best practice: bật MFA, không dùng hàng ngày, tạo IAM Administrator riêng, khóa credential root.
- Thành thạo **AWS IAM**:
  - Principal types: Root, IAM User, IAM Role, Federated User, AWS Service
  - Policy types: Identity-based & Resource-based
  - Quy tắc đánh giá: Explicit Deny > Allow > Default Deny
  - IAM Role + Trust Policy + STS để cấp quyền tạm thời và cross-account
  - Sử dụng IAM Role cho EC2, Lambda… thay vì hard-code Access Key
- Nắm vững **AWS Organizations**:
  - Tạo và quản lý nhiều AWS account tập trung
  - Tổ chức theo OU, áp dụng Service Control Policy (SCP) để giới hạn quyền tối đa
  - Consolidated Billing
- Thành thạo **AWS Identity Center** (trước đây là AWS SSO):
  - Identity source: Built-in, AWS Managed Microsoft AD, AD Connector, External IdP
  - Permission Sets → tự động tạo IAM Role trong từng account thành viên
- Hiểu rõ **Amazon Cognito**:
  - User Pool → đăng ký/đăng nhập người dùng ứng dụng
  - Identity Pool → cấp quyền tạm thời truy cập AWS services
- Làm chủ **AWS KMS**:
  - Customer Managed Keys (CMK), FIPS 140-2
  - Tạo Data Key để mã hóa dữ liệu lớn bên ngoài KMS
  - Encryption at rest cho hầu hết các dịch vụ AWS
- Sử dụng **AWS Security Hub**:
  - Kiểm tra bảo mật liên tục theo AWS Foundational Security Best Practices và các chuẩn CIS, PCI DSS…
  - Cung cấp security score và danh sách tài nguyên cần khắc phục

Thực hành thành công:
- Tạo Organization + OU + SCP
- Cấu hình Identity Center + Permission Sets
- Tạo Cognito User Pool & Identity Pool
- Dùng KMS mã hóa EBS, S3
- Kích hoạt và phân tích kết quả Security Hub