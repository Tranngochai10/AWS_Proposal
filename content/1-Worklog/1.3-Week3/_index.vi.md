---
title: "Worklog Tuần 3"
date: 2025-09-09
weight: 1
chapter: false
pre: " <b> 1.3. </b> "
---
### Week 3 Objectives:
- Làm quen với các thành viên First Cloud Journey
- Nắm vững các dịch vụ cơ bản của AWS, cách sử dụng AWS Management Console & AWS CLI

### Tasks to be carried out this week:
| Day | Task                                                                                                                                                                                                   | Start Date   | Completion Date | Reference Material                        |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------ | --------------- | ----------------------------------------- |
| 2   | - Làm quen với các thành viên FCJ <br> - Đọc và ghi chú nội quy thực tập                                                                                                                         | 08/11/2025   | 08/11/2025      |                                           |
| 3   | - Tìm hiểu tổng quan về AWS và các nhóm dịch vụ chính (Compute, Storage, Networking, Database…)                                                                                                         | 08/12/2025   | 08/12/2025      | https://cloudjourney.awsstudygroup.com/   |
| 4   | - Tạo tài khoản AWS Free Tier <br> - Làm quen AWS Console & AWS CLI <br> - Thực hành: tạo tài khoản, cài đặt và cấu hình AWS CLI                                                                      | 08/13/2025   | 08/13/2025      | https://cloudjourney.awsstudygroup.com/   |
| 5   | - Tìm hiểu sâu về Amazon EC2 (Instance types, AMI, EBS, Key Pair, Instance Store, User Data, Metadata, Pricing models…) <br> - Các dịch vụ liên quan: Lightsail, EFS, FSx, Application Migration Service | 08/14/2025   | 08/16/2025      | https://cloudjourney.awsstudygroup.com/   |
| 6   | - Thực hành: <br>&emsp; + Khởi tạo EC2 instance <br>&emsp; + Kết nối SSH/RDP <br>&emsp; + Gắn thêm EBS volume <br>&emsp; + Tạo snapshot và AMI                                                        | 08/15/2025   | 08/16/2025      | https://cloudjourney.awsstudygroup.com/   |

### Week 3 Achievements:

Hoàn thành 100% kế hoạch tuần 3 với các nội dung nổi bật sau:

- Hiểu rõ bản chất và vai trò của **Amazon EC2 (EC2)**: là dịch vụ cung cấp máy chủ ảo với khả năng khởi tạo nhanh, co giãn linh hoạt, có thể thay thế hoàn toàn máy chủ vật lý cho hầu hết các workload (web, app, database, authentication…).
- Nắm vững cách cấu hình phần cứng của EC2 thông qua **Instance Type** (quyết định CPU, Memory, Network, Storage) và các yếu tố liên quan như Hypervisor (Nitro/KVM/HVM/PV), Placement Group, Availability Zone.
- Hiểu rõ về **AMI (Amazon Machine Image)**: chứa root volume OS + launch permission + block device mapping; có thể dùng AMI có sẵn của AWS, Marketplace hoặc tự tạo; backup EC2 bằng cách tạo AMI hoặc snapshot.
- Thành thạo **Key Pair**: cách hoạt động với Linux (SSH + private key) và Windows (mật khẩu Admin được mã hóa bằng public key).
- Nắm chắc **Amazon EBS (Elastic Block Store)**:
  - Block storage độc lập với EC2, kết nối qua mạng riêng trong cùng AZ
  - Hai nhóm chính: SSD và HDD, độ sẵn sàng 99.99% nhờ replicate 3 node
  - Hỗ trợ Multi-Attach trên Nitro instance
  - Backup bằng snapshot (full → incremental) lưu trên S3
- Hiểu sự khác biệt với **Instance Store**: NVMe tốc độ cực cao, gắn trực tiếp trên physical host, mất dữ liệu khi Stop (nhưng không mất khi Reboot), phù hợp buffer/cache/swap/temporary data.
- Biết cách dùng **User Data** script (bash/PowerShell) chạy 1 lần khi khởi tạo instance và **Instance Metadata** để tự động cấu hình (hostname, IP…).
- Nắm các mô hình định giá EC2 & Auto Scaling:
  - On-Demand, Reserved Instance Saving Plans Spot Instance
  - Auto Scaling Group hỗ trợ nhiều pricing model cùng lúc, hoạt động multi-AZ, tự đăng ký vào ELB
- Tìm hiểu các dịch vụ liên quan:
  - **Amazon Lightsail**: chi phí thấp, phù hợp workload nhẹ, đi kèm data transfer rẻ, backup bằng snapshot, VPC peering 1-click
  - **EFS**: NFSv4 network filesystem, multi-attach Linux, tính phí theo dung lượng thực dùng, hỗ trợ on-prem qua DX/VPN
  - **FSx**: NTFS/SMB filesystem cho Windows & Linux, tính phí theo dung lượng thực, có deduplication tiết kiệm 30-50%
  - **AWS Application Migration Service (MGN)**: replicate liên tục máy chủ vật lý/ảo lên AWS để phục vụ migration & DR, sử dụng staging instance nhỏ, tự động cut-over
- Thực hành thành công: khởi tạo EC2, kết nối SSH, gắn EBS, tạo snapshot & AMI.