---
title: "Worklog Tuần 6"
date: 2025-09-09
weight: 6
chapter: false
pre: " <b> 1.6. </b> "
---
### Week 6 Objectives:
- Nắm vững khái niệm cơ bản và nâng cao về cơ sở dữ liệu
- Phân biệt rõ OLTP vs OLAP, RDBMS vs NoSQL
- Thành thạo toàn bộ dịch vụ cơ sở dữ liệu quan trọng trên AWS: RDS, Aurora, Redshift, ElastiCache

### Tasks to be carried out this week:
| Day | Task                                                                                                             | Start Date   | Completion Date | Reference Material                        |
| --- | ---------------------------------------------------------------------------------------------------------------- | ------------ | --------------- | ----------------------------------------- |
| 1–2 | Khái niệm CSDL: Session, Primary Key, Foreign Key, Index, Partition, Execution Plan, Buffer, DB Log              | 01–02/09/2025| 02/09/2025      | https://cloudjourney.awsstudygroup.com/   |
| 3   | RDBMS vs NoSQL, OLTP vs OLAP                                                                                     | 03/09/2025   | 03/09/2025      |                                           |
| 4   | Amazon RDS + Aurora (MySQL & PostgreSQL compatible)                                                              | 04/09/2025   | 04/09/2025      |                                           |
| 5   | Amazon Redshift – Data Warehouse & OLAP                                                                          | 05/09/2025   | 05/09/2025      |                                           |
| 6   | Amazon ElastiCache (Redis & Memcached)                                                                          | 06/09/2025   | 06/09/2025      |                                           |

### Week 6 Achievements:

Hoàn thành xuất sắc 100 % nội dung tuần 6 với các kiến thức cốt lõi sau:

- Hiểu sâu các khái niệm nền tảng CSDL:
  - Primary Key / Foreign Key / Index / Partition / Execution Plan / Buffer / DB Log
  - Session, OLTP (giao dịch nhanh, nhiều read-write nhỏ), OLAP (phân tích phức tạp trên dữ liệu lịch sử lớn)
  - RDBMS (bảng, quan hệ, SQL) vs NoSQL (document, key-value, column-family, graph)

- Thành thạo **Amazon RDS** (Managed Relational Database Service):
  - Hỗ trợ MySQL, PostgreSQL, MariaDB, Oracle, SQL Server, và Aurora
  - Tự động backup (database + log, max 35 ngày), Read Replica, Multi-AZ failover
  - Storage auto-scaling, mã hóa at rest & in transit, bảo vệ bằng Security Group
  - Phù hợp nhất cho workload OLTP

- Làm chủ **Amazon Aurora**:
  - Engine tương thích MySQL & PostgreSQL nhưng tối ưu storage layer cho hiệu năng đọc/ghi song song cực cao
  - Tính năng nổi bật: Backtrack, Aurora Clone, Global Database, Multi-Master
  - Vẫn nằm trong RDS → thừa hưởng tất cả tính năng quản lý của RDS

- Hiệu năng vượt trội so với RDS thông thường

- Hiểu rõ **Amazon Redshift**:
  - Data warehouse được quản lý hoàn toàn, tối ưu cho OLAP
  - Kiến trúc MPP (Massively Parallel Processing) + columnar storage
  - Leader Node điều phối, Compute Nodes lưu trữ + xử lý song song
  - Hỗ trợ JDBC/ODBC, Redshift Spectrum, transient cluster để tiết kiệm chi phí

- Thành thạo **Amazon ElastiCache**:
  - Managed in-memory cache hỗ trợ Redis và Memcached
  - Tự động thay thế node lỗi, Multi-AZ
  - Đặt trước tầng database để giảm tải OLTP
  - Ưu tiên dùng Redis cho ứng dụng mới (tính năng phong phú hơn)

Thực hành thành công:
- Tạo RDS MySQL + Read Replica + Multi-AZ
- Tạo Aurora cluster + Global Database demo
- Tạo Redshift cluster + chạy query OLAP
- Tạo ElastiCache Redis cluster và tích hợp với ứng dụng mẫu