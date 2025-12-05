---
title : "Cấu hình API Gateway"
date : 2025-09-09
weight : 5
chapter : false
pre : " <b> 5.5. </b> "
---

## Cấu hình API Gateway

Bây giờ chúng ta sẽ tạo một REST API trong API Gateway và kết nối nó với các Lambda functions của chúng ta.

### Bước 1: Tạo REST API

1. Vào dịch vụ **API Gateway**
2. Nhấp **Create API**
3. Chọn **REST API** → **Build**
4. Chọn **New API**
5. API name: `TaskManagementAPI`
6. Description: `Serverless REST API for Task Management`
7. Endpoint Type: **Regional**
8. Nhấp **Create API**

### Bước 2: Tạo Resources

1. Trong API, bạn sẽ thấy root resource `/`
2. Nhấp **Actions** → **Create Resource**
3. Resource name: `tasks`
4. Resource path: `tasks`
5. Bật **API Gateway CORS**
6. Nhấp **Create Resource**

### Bước 3: Tạo Methods

#### Tạo POST Method (Create Task)

1. Chọn resource `/tasks`
2. Nhấp **Actions** → **Create Method**
3. Chọn **POST** → Nhấp dấu check
4. Integration type: **Lambda Function**
5. Lambda Region: Region của bạn
6. Lambda Function: `createTask`
7. Bật **Use Lambda Proxy Integration**
8. Nhấp **Save** → **OK** (khi được nhắc thêm quyền)

#### Tạo GET Method (List Tasks)

1. Chọn resource `/tasks`
2. Nhấp **Actions** → **Create Method**
3. Chọn **GET** → Nhấp dấu check
4. Integration type: **Lambda Function**
5. Lambda Function: `listTasks`
6. Bật **Use Lambda Proxy Integration**
7. Nhấp **Save** → **OK**

#### Tạo GET Method (Get Single Task)

1. Chọn resource `/tasks`
2. Nhấp **Actions** → **Create Resource**
3. Resource name: `{id}`
4. Resource path: `{id}`
5. Bật **API Gateway CORS**
6. Nhấp **Create Resource**
7. Chọn resource `/tasks/{id}`
8. Tạo **GET** method → Kết nối với function `getTask`
9. Tạo **PUT** method → Kết nối với function `updateTask`
10. Tạo **DELETE** method → Kết nối với function `deleteTask`

### Bước 4: Bật CORS

1. Chọn resource `/tasks`
2. Nhấp **Actions** → **Enable CORS**
3. Chấp nhận cài đặt mặc định
4. Nhấp **Enable CORS and replace existing CORS headers**

### Bước 5: Deploy API

1. Nhấp **Actions** → **Deploy API**
2. Deployment stage: **New Stage**
3. Stage name: `dev`
4. Stage description: `Development stage`
5. Nhấp **Deploy**

### Bước 6: Lấy API Endpoint

Sau khi deploy, bạn sẽ thấy **Invoke URL**. Đây là endpoint API của bạn.

Ví dụ: `https://abc123xyz.execute-api.us-east-1.amazonaws.com/dev`

### API Endpoints

API của bạn sẽ có các endpoint sau:

- `POST /tasks` - Tạo task mới
- `GET /tasks` - Liệt kê tất cả tasks
- `GET /tasks/{id}` - Lấy thông tin một task cụ thể
- `PUT /tasks/{id}` - Cập nhật task
- `DELETE /tasks/{id}` - Xóa task

### Kiểm thử API

Bạn có thể kiểm thử API bằng:

1. **API Gateway Console** - Sử dụng tính năng "Test"
2. **Postman** - Import API và kiểm thử endpoints
3. **curl** - Sử dụng dòng lệnh
4. **Browser** - Cho các GET requests

### Ví dụ cURL Commands

```bash
# Tạo một task
curl -X POST https://your-api-id.execute-api.region.amazonaws.com/dev/tasks \
  -H "Content-Type: application/json" \
  -d '{"title": "Learn AWS", "description": "Complete Lambda workshop", "status": "pending"}'

# Liệt kê tất cả tasks
curl https://your-api-id.execute-api.region.amazonaws.com/dev/tasks

# Lấy một task cụ thể
curl https://your-api-id.execute-api.region.amazonaws.com/dev/tasks/{task-id}

# Cập nhật task
curl -X PUT https://your-api-id.execute-api.region.amazonaws.com/dev/tasks/{task-id} \
  -H "Content-Type: application/json" \
  -d '{"title": "Updated title", "status": "completed"}'

# Xóa task
curl -X DELETE https://your-api-id.execute-api.region.amazonaws.com/dev/tasks/{task-id}
```

### Bước tiếp theo

Kiểm thử API của bạn kỹ lưỡng, sau đó tiếp tục phần cleanup để xóa các tài nguyên.
