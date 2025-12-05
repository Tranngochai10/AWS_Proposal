---
title : "Kiểm thử và Dọn dẹp"
date : 2025-09-09
weight : 6
chapter : false
pre : " <b> 5.6. </b> "
---

## Kiểm thử và Dọn dẹp

### Kiểm thử API của bạn

Trước khi dọn dẹp, đảm bảo kiểm thử tất cả các endpoints:

1. **Create Task** - POST request đến `/tasks`
2. **List Tasks** - GET request đến `/tasks`
3. **Get Task** - GET request đến `/tasks/{id}`
4. **Update Task** - PUT request đến `/tasks/{id}`
5. **Delete Task** - DELETE request đến `/tasks/{id}`

### Các bước Dọn dẹp

Để tránh phát sinh chi phí, hãy xóa tất cả các tài nguyên đã tạo trong workshop này.

#### Bước 1: Xóa API Gateway

1. Vào **API Gateway** console
2. Chọn API của bạn: `TaskManagementAPI`
3. Nhấp **Actions** → **Delete API**
4. Nhập tên API để xác nhận
5. Nhấp **Delete**

#### Bước 2: Xóa Lambda Functions

1. Vào **Lambda** console
2. Xóa từng function:
   - `createTask`
   - `listTasks`
   - `getTask`
   - `updateTask`
   - `deleteTask`

Với mỗi function:
- Chọn function
- Nhấp **Delete**
- Nhập "delete" để xác nhận
- Nhấp **Delete**

#### Bước 3: Xóa DynamoDB Table

1. Vào **DynamoDB** console
2. Chọn table: `tasks`
3. Nhấp **Delete**
4. Nhập "delete" để xác nhận
5. Nhấp **Delete**

#### Bước 4: Xóa IAM Role

1. Vào **IAM** console
2. Nhấp **Roles**
3. Tìm role: `lambda-dynamodb-role`
4. Nhấp vào role
5. Nhấp **Delete**
6. Nhập tên role để xác nhận
7. Nhấp **Delete**

#### Bước 5: Xóa CloudWatch Log Groups (Tùy chọn)

1. Vào **CloudWatch** console
2. Nhấp **Log groups**
3. Xóa log groups cho mỗi Lambda function:
   - `/aws/lambda/createTask`
   - `/aws/lambda/listTasks`
   - `/aws/lambda/getTask`
   - `/aws/lambda/updateTask`
   - `/aws/lambda/deleteTask`

### Xác minh

Sau khi dọn dẹp, xác minh rằng:
- ✅ Không có API Gateway APIs nào tồn tại
- ✅ Không có Lambda functions nào tồn tại
- ✅ Không có DynamoDB tables nào tồn tại
- ✅ IAM role đã được xóa

### Tóm tắt

Chúc mừng! Bạn đã thành công:

1. ✅ Tạo DynamoDB table để lưu trữ dữ liệu
2. ✅ Tạo Lambda functions cho business logic
3. ✅ Cấu hình API Gateway REST API
4. ✅ Tích hợp Lambda với API Gateway
5. ✅ Xây dựng một REST API serverless hoàn chỉnh

### Những gì bạn đã học

- Cách tạo và cấu hình DynamoDB tables
- Cách viết Lambda functions bằng Python
- Cách tạo REST APIs với API Gateway
- Cách tích hợp Lambda với API Gateway
- Cách xử lý HTTP requests và responses
- Các mẫu kiến trúc serverless

### Bước tiếp theo

- Thêm xác thực sử dụng AWS Cognito
- Thêm API rate limiting
- Triển khai input validation
- Thêm error handling và logging
- Deploy lên production stage
- Thiết lập monitoring và alerts

Cảm ơn bạn đã hoàn thành workshop này!
