---
title : "Giới thiệu"
date :  2025-09-09 
weight : 1
chapter : false
pre : " <b> 5.1. </b> "
---

## Tổng quan Workshop

### Serverless là gì?

**Serverless computing** (Điện toán không máy chủ) là mô hình điện toán đám mây nơi nhà cung cấp đám mây quản lý hạ tầng, tự động cung cấp, mở rộng và quản lý server. Bạn chỉ trả tiền cho thời gian tính toán bạn sử dụng.

### Tổng quan Kiến trúc

Trong workshop này, chúng ta sẽ xây dựng một REST API serverless với kiến trúc sau:

```
Client Request (Yêu cầu từ Client)
    ↓
API Gateway (REST API)
    ↓
Lambda Function (Logic nghiệp vụ)
    ↓
DynamoDB (Lưu trữ dữ liệu)
```

### Các thành phần

#### 1. **Amazon API Gateway**
- Tạo RESTful APIs
- Xử lý HTTP requests và responses
- Quản lý xác thực và phân quyền
- Cung cấp throttling và monitoring

#### 2. **AWS Lambda**
- Dịch vụ tính toán serverless
- Thực thi code để phản hồi events
- Tự động mở rộng dựa trên lưu lượng
- Chỉ trả tiền cho thời gian tính toán sử dụng

#### 3. **Amazon DynamoDB**
- Dịch vụ cơ sở dữ liệu NoSQL
- Được quản lý hoàn toàn và serverless
- Nhanh và có khả năng mở rộng
- Tự động scaling

### Những gì chúng ta sẽ xây dựng

Một **Task Management API** với các endpoint sau:

- `POST /tasks` - Tạo task mới
- `GET /tasks` - Liệt kê tất cả tasks
- `GET /tasks/{id}` - Lấy thông tin một task cụ thể
- `PUT /tasks/{id}` - Cập nhật task
- `DELETE /tasks/{id}` - Xóa task

### Lợi ích của Kiến trúc Serverless

- **Không cần quản lý server** - AWS xử lý toàn bộ hạ tầng
- **Tự động mở rộng** - Tự động xử lý các đợt tăng lưu lượng
- **Tiết kiệm chi phí** - Chỉ trả tiền cho những gì bạn sử dụng
- **Tính sẵn sàng cao** - Có sẵn tính dự phòng và khả năng chịu lỗi
- **Phát triển nhanh** - Tập trung vào code, không phải hạ tầng
