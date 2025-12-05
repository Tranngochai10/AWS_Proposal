---
title: "Blog 1"
date: 2025-09-09
weight: 1
chapter: false
pre: " <b> 3.1. </b> "
---
# Python 3.13 runtime hiện đã có sẵn trong AWS Lambda

bởi Julian Wood | vào ngày 14 THÁNG 11 2024 | trong Announcements, AWS Cloud Development Kit, AWS Lambda, AWS SDK for Python, AWS Serverless Application Model, Python, Serverless | Permalink | Share

Bài viết này được viết bởi Julian Wood, Principal Developer Advocate, và Leandro Cavalcante Damascena, Senior Solutions Architect Engineer.

AWS Lambda hiện đã hỗ trợ Python 3.13 như là một managed runtime và container base image. Python là một ngôn ngữ phổ biến để xây dựng các ứng dụng serverless. Bản phát hành Python 3.13 bao gồm một số thay đổi đối với ngôn ngữ, việc triển khai và thư viện chuẩn. Với bản phát hành này, các nhà phát triển Python giờ đây có thể tận dụng các tính năng và cải tiến mới này khi tạo các ứng dụng serverless trên Lambda. Python 3.13 cũng bao gồm hỗ trợ thử nghiệm cho một số tính năng, nhưng các tính năng này không có sẵn trong Lambda.

Bạn có thể phát triển các Lambda functions trong Python 3.13 bằng cách sử dụng AWS Management Console, AWS Command Line Interface (AWS CLI), AWS SDK for Python (Boto3), AWS Serverless Application Model (AWS SAM), AWS Cloud Development Kit (AWS CDK), và các công cụ infrastructure as code khác.

Python 3.13 runtime cho phép bạn triển khai các serverless best practices bằng cách sử dụng Powertools for AWS Lambda (Python). Đây là một developer toolkit bao gồm observability, batch processing, AWS Systems Manager Parameter Store integration, idempotency, feature flags, Amazon CloudWatch Metrics, structured logging, và nhiều hơn nữa.

Lambda@Edge cho phép bạn sử dụng Python 3.13 để tùy chỉnh nội dung độ trễ thấp được phân phối thông qua Amazon CloudFront.

## Thay đổi Lambda runtime

### Amazon Linux 2023
Giống như Python 3.12 runtime, Python 3.13 runtime được dựa trên provided.al2023 runtime, được xây dựng dựa trên Amazon Linux 2023 minimal container image. Amazon Linux 2023 minimal image sử dụng microdnf làm package manager, được symlink như dnf. Điều này thay thế yum package manager được sử dụng trong Python 3.11 và các AL2-based images trước đó. Nếu bạn deploy các Lambda functions của mình dưới dạng container images, bạn phải cập nhật Dockerfiles của mình để sử dụng dnf thay vì yum khi nâng cấp lên Python 3.13 base image từ Python 3.11 hoặc các base images trước đó.

Tìm hiểu thêm về provided.al2023 runtime trong bài blog post Introducing the Amazon Linux 2023 runtime for AWS Lambda và Amazon Linux 2023 launch blog post.

## Các tính năng Python mới

### Cải tiến Data model
Có những cải tiến đối với Python data model. _static_attributes_ lưu trữ tên của các attributes được truy cập thông qua self.X trong bất kỳ function nào trong một class body.

### Thay đổi Typing
Với việc triển khai PEP 702, bạn giờ đây có thể sử dụng decorator warnings.deprecated() mới để đánh dấu các deprecations trong type system và tại runtime.

Python 3.13 cũng thêm PEP 696, giới thiệu các giá trị mặc định cho type parameters. Cải tiến này cho phép các nhà phát triển chỉ định các default types cho TypeVar, ParamSpec, và TypeVarTuple khi bỏ qua type arguments.

### Standard library
Standard library bao gồm các cải tiến cho một exception PythonFinalizationError mới, được raised khi một operation bị chặn trong quá trình finalization.

Các functions mới base64.z85encode() và base64.z85decode() hỗ trợ encoding và decoding Z85 data.

Module copy giờ đây có một function copy.replace(), với hỗ trợ cho nhiều built-in types và bất kỳ class nào định nghĩa method _replace()_.

Module os có a suite of new functions để làm việc với các timer notification file descriptors của Linux.

Có một thay đổi đối với các mutation semantics được định nghĩa cho locals().

## Các tính năng thử nghiệm không khả dụng
Python 3.13 bao gồm một số tính năng thử nghiệm không được bật cho Lambda managed runtime hoặc base images. Các tính năng này phải được bật khi Python runtime được compile. Vì Lambda-provided Python 3.13 runtime được thiết kế cho production workloads, các tính năng này không được bật trong Lambda build của Python 3.13 và không thể được bật thông qua execution-time flag. Để sử dụng các tính năng này trong Lambda, bạn có thể deploy Python runtime của riêng mình bằng cách sử dụng custom runtime hoặc container image với các tính năng này được bật.

### Free-threaded CPython
Bạn không thể bật hỗ trợ thử nghiệm để chạy Python ở free-threaded mode, với global interpreter lock (GIL) bị vô hiệu hóa.

### Just-in-time (JIT) compiler
Bạn cũng không thể bật experimental JIT compiler trong Lambda managed runtime hoặc base image.

## Cân nhắc về Performance
Khi ra mắt, các Lambda runtimes mới nhận được ít lượng sử dụng hơn so với các runtimes hiện có đã được thiết lập. Điều này có thể dẫn đến thời gian cold start dài hơn do giảm cache residency trong các sub-systems Lambda nội bộ. Thời gian cold start thường được cải thiện trong những tuần sau khi ra mắt khi lượng sử dụng tăng lên. Do đó, AWS khuyến nghị không rút ra kết luận từ các so sánh hiệu suất song song với các Lambda runtimes khác cho đến khi hiệu suất đã ổn định. Vì hiệu suất phụ thuộc rất nhiều vào workload, khách hàng có workloads nhạy cảm về hiệu suất nên tiến hành thử nghiệm của riêng họ, thay vì dựa vào các test benchmarks chung.

## Sử dụng Python 3.13 trong Lambda

### AWS Management Console
Để sử dụng Python 3.13 runtime để phát triển các Lambda functions của bạn, chỉ định giá trị runtime parameter là Python 3.13 khi tạo hoặc cập nhật một function. Phiên bản Python 3.13 có sẵn trong dropdown Runtime trong trang Create Function.

Để cập nhật một Lambda function hiện có lên Python 3.13, điều hướng đến function trong Lambda console và chọn Edit trong panel Runtime settings. Phiên bản Python mới có sẵn trong dropdown Runtime.

Bạn có thể cần kiểm tra code và dependencies của mình để đảm bảo tương thích với Python 3.13, và cập nhật khi cần thiết.

### AWS Lambda container image
Thay đổi phiên bản Python base image bằng cách sửa đổi câu lệnh FROM trong Dockerfile của bạn.

```dockerfile
FROM public.ecr.aws/lambda/python:3.13
# Copy function code
COPY lambda_handler.py ${LAMBDA_TASK_ROOT}