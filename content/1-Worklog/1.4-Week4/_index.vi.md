---
title: "Worklog Tuần 4"
date: 2025-09-09
weight: 1
chapter: false
pre: " <b> 1.4. </b> "
---
### Week 4 Objectives:
- Nắm vững Amazon Simple Storage Service (S3) và toàn bộ hệ sinh thái liên quan
- Hiểu rõ khái niệm object storage, các lớp lưu trữ, quản lý vòng đời, bảo mật và tối ưu hiệu năng
- Tìm hiểu AWS Snow Family, Storage Gateway và các khái niệm Disaster Recovery

### Tasks to be carried out this week:
| Day | Task                                                                                                                                                                                                                   | Start Date   | Completion Date | Reference Material                        |
| --- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------ | --------------- | ----------------------------------------- |
| 1–2 | Tìm hiểu sâu Amazon S3: kiến trúc, độ bền, storage class, lifecycle, versioning, static website, CORS, bucket policy, ACL, Access Point, VPC endpoint                                                                   | 18–19/08/2025| 19/08/2025      | https://cloudjourney.awsstudygroup.com/      |
| 3   | Tối ưu hiệu năng S3, multipart upload, thiết kế prefix, event notification, replication (CRR/SRR)                                                                                                                      | 20/08/2025   | 20/08/2025      |                                           |
| 4   | Amazon S3 Glacier (Instant Retrieval, Flexible Retrieval, Deep Archive) và các tùy chọn retrieve (Expedited, Standard, Bulk)                                                                                            | 21/08/2025   | 21/08/2025      |                                           |
| 5   | AWS Snow Family (Snowball, Snowball Edge, Snowmobile) và AWS Storage Gateway (File, Volume, Tape)                                                                                                                      | 22/08/2025   | 22/08/2025      |                                           |
| 6   | Khái niệm Disaster Recovery (RTO/RPO), 4 chiến lược DR trên AWS, dịch vụ AWS Backup                                                                                                                                   | 23/08/2025   | 23/08/2025      |                                           |

### Week 4 Achievements:

Hoàn thành 100 % kế hoạch tuần 4 với các nội dung nổi bật sau:

- Hiểu rõ bản chất **Amazon S3** là kho lưu trữ dạng object (không phải block/file), mô hình write-once-read-many, dung lượng không giới hạn, mỗi object tối đa 5 TB, dữ liệu tự động nhân bản trên ít nhất 3 AZ trong region.
- Đạt độ bền 99.999999999 % (11×9s) và độ sẵn sàng 99.99 %.
- Thành thạo các lớp lưu trữ S3:
  - S3 Standard, Standard-IA, One Zone-IA, Intelligent-Tiering
  - Glacier Instant Retrieval, Flexible Retrieval, Deep Archive
- Biết sử dụng **Lifecycle Policy** để tự động chuyển lớp hoặc hết hạn object theo ngày.
- Nắm vững các tính năng nâng cao:
  - Versioning (chống xóa nhầm, chống ransomware)
  - Static website hosting (phù hợp SPA – React, Angular…)
  - CORS configuration
  - Event notifications, multipart upload
  - S3 Access Points, VPC Endpoint (truy cập private)
- Kiểm soát truy cập: Bucket Policy + IAM Policy (ưu tiên dùng), S3 ACL (legacy), Block Public Access.
- Tối ưu hiệu năng S3 bằng cách dùng random prefix để phân bố object đều trên nhiều partition.
- Hiểu rõ **Amazon S3 Glacier**:
  - Chi phí cực thấp cho dữ liệu lưu trữ dài hạn
  - 3 tùy chọn retrieve: Expedited (1–5 phút), Standard (3–5 giờ), Bulk (5–12 giờ)
- Nắm vững **AWS Snow Family**:
  - Snowball ~80 TB, Snowball Edge ~100 TB + có compute, Snowmobile tới 100 PB/thùng container
- Thành thạo **AWS Storage Gateway** – giải pháp hybrid:
  - File Gateway → S3 (NFS/SMB)
  - Volume Gateway → S3 (iSCSI) → snapshot thành EBS
  - Tape Gateway → Virtual Tape Library (S3/Glacier)
- Nắm chắc khái niệm Disaster Recovery:
  - RTO (thời gian phục hồi tối đa chấp nhận được)
  - RPO (mức mất dữ liệu tối đa chấp nhận được)
  - 4 chiến lược DR trên AWS: Backup & Restore → Pilot Light → Warm Standby → Multi-Site Active/Active
  - AWS Backup: quản lý tập trung backup cho EC2, EBS, RDS, DynamoDB, EFS, Storage Gateway…

Thực hành thành công:
- Tạo bucket + bật versioning + lifecycle + static website
- Cấu hình bucket policy, CORS, VPC endpoint
- Thử multipart upload và event trigger
- Khám phá giao diện AWS Backup