---
title: "Blog 2"
date: 2025-09-09
weight: 1
chapter: false
pre: " <b> 3.2. </b> "
---

# Triển khai custom domain names cho private endpoints với Amazon API Gateway

bởi Chris McPeek | vào ngày 21 THÁNG 11 2024 | trong Amazon API Gateway, Amazon EC2, Amazon Elastic Container Service, Amazon Elastic Kubernetes Service, AWS Lambda, Resource Access Manager (RAM), Serverless | Permalink | Share

Bài viết này được viết bởi Heeki Park, Principal Solutions Architect  
1/23/25: Bài viết này đã được cập nhật để sửa các AWS CloudFormation templates.

Amazon API Gateway đang giới thiệu hỗ trợ custom domain name cho private REST API endpoints. Khách hàng chọn private REST API endpoints khi họ muốn các endpoints chỉ có thể được gọi từ bên trong Amazon VPC của họ. Custom domain names là các URL đơn giản và trực quan hơn mà bạn có thể sử dụng với ứng dụng của mình và trước đây chỉ được hỗ trợ với public REST API endpoints. Giờ đây bạn có thể sử dụng custom domain names để ánh xạ tới private REST APIs và chia sẻ các custom domain names đó giữa các accounts bằng cách sử dụng AWS Resource Access Manager (AWS RAM).

## Tổng quan về kết nối API Gateway

Khi xem xét kết nối mạng với API Gateway, có hai khía cạnh quan trọng cần lưu ý: integration type và connectivity type. Sơ đồ sau đây cho thấy các ví dụ về những cân nhắc đó.

Figure 1: Overall architecture

Khía cạnh đầu tiên là sự phân biệt giữa frontend integrations và backend integrations. Frontend integrations là cách các API clients như thiết bị di động, trình duyệt web, hoặc ứng dụng client kết nối với API endpoint. Backend integrations là các API services mà API Gateway endpoint của bạn proxy các requests tới, như các ứng dụng chạy trên Amazon Elastic Compute Cloud (EC2) instances, Amazon Elastic Kubernetes Service (EKS) hoặc Amazon Elastic Container Service (ECS) containers, hoặc dưới dạng AWS Lambda functions. Khía cạnh thứ hai là liệu kết nối đó có thông qua public internet hay thông qua private VPC của bạn.

## Gọi private REST API endpoints

Để gửi requests tới một private REST API endpoint, clients phải hoạt động trong một VPC được cấu hình với một VPC endpoint. Khi VPC endpoint được cấu hình, một client có three different options trong VPC để kết nối với API endpoint, tùy thuộc vào cách VPC và VPC endpoint được cấu hình.

Nếu VPC endpoint có private DNS được bật, client có thể gửi requests tới standard endpoint URL: https://{api-id}.execute-api.{region}.amazonaws.com/{stage}. Các requests này sẽ resolve tới VPC endpoint, sau đó được route tới API Gateway endpoint thích hợp.

Hình 2: VPC endpoint được cấu hình với private DNS names được bật

Ngoài ra, nếu VPC endpoint có private DNS bị tắt, client có thể gửi requests tới VPC endpoint URL: https://{vpce-id}.execute-api.{region}.amazonaws.com/{stage}. Một trong các headers sau cũng cần được gửi kèm với request đó.  
Host: {api-id}.execute-api.us-east-1.amazonaws.com  
x-apigw-api-id: {api-id}

Cuối cùng, nếu VPC endpoint có private DNS bị tắt và private REST API endpoint được liên kết với VPC endpoint, client có thể gửi requests tới URL sau: https://{api-id}-{vpce-id}.execute-api.{region}.amazonaws.com/{stage}. Để liên kết một VPC endpoint với một private API, property sau cấu hình liên kết đó.

```yaml
     EndpointConfiguration:
        Type: PRIVATE
        VPCEndpointIds:
          - !Ref vpcEndpointId
```