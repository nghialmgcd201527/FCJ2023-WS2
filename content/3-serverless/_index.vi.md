---
title: "Giới thiệu nhanh về ứng dụng web serverless"
date: "`r Sys.Date()`"
weight: 3
chapter: false
pre: " <b> 3. </b> "
---

#### Tổng quan

Mục tiêu của phần này là giới thiệu cho các bạn ứng dụng web cơ bản về serverless và hiểu được cách mà các services **AWS Serverless** tương tác với nhau. Chúng ta sẽ bắt đầu bước này bằng cách giúp bạn làm quen với các phần chuyển động của environtment của ứng dụng web Serverless nói chung. Trong các phần tiếp theo, bạn sẽ sử dụng ứng dụng web này để thêm các tính năng cần thiết để xây dựng ứng dụng SaaS của chúng ta.

Trong phần này, chúng ta sẽ sử dụng Serverless Application Model (SAM) để xây dựng một quy trình backend để xử lí các yêu cầu từ ứng dụng web. Bạn sẽ dùng Lambda function để thực hiện mỗi chức năng mà ứng dụng cần, mỗi lần user gửi request đến, nó sẽ được gọi thực thi. Funtion này sẽ lưu trữ dữ liệu vào DynamoDB, sau đó sẽ gửi phản hồi đến phần front-end và cập nhật trên giao diện người dùng. Function được gọi từ trình duyệt bằng Amazon API Gateway.

#### SAM là gì?

[Serverless Application Model (SAM)](https://aws.amazon.com/serverless/sam/) là một open-source framework nó sẽ giúp việc triển khai serverless application trở nên dễ dàng hơn. Nó cung cấp một cách đơn giản để định nghĩa các serverless application, và cung cấp một tập các công cụ để triển khai các ứng dụng đó.

Nó cho phép chúng ta xác định rõ những yêu cầu của ứng dụng bằng code. SAM chuyển đổi và mở rộng SAM syntax lên AWS Cloudformation để triển khai ứng dụng của bạn. Bạn sẽ thấy và sử dụng SAM templates throughout this workshop.

#### SAM hoạt động như thế nào?

AWS SAM dựa trên AWS Cloudformation. Một ứng dụng serverless được định nghĩa bằng một CloudFormation template và được triển khai với CloudFormation stack. Tóm lại, AWS SAM template là CloudFormation template.

AWS SAM xác định một tập hợp tài nguyên mô tả các components chung của ứng dụng serverless. Để AWS SAM có những objects được định nghĩa trong CloudFormation template thì template đó phải gồm phần Transform trong document root là `AWS::Serverless-2016-10-31`.

{{% notice tip %}}
Trong bài này chúng ta sẽ không đi sâu vào phân tích triển khai một ứng dụng web Serverless với SAM template, nên nếu bạn chưa có kiến thức gì về SAM template thì [hãy tham khảo ở đây](https://catalog.us-east-1.prod.workshops.aws/workshops/841ce16b-9d86-48ac-a3f6-6a1b29f95d2b/en-US/step-1) để nắm rõ cấu trúc và nội dụng của các file mà mình sẽ chỉ việc chạy script để không mất nhiều thời gian trong bài workshop này.

{{% /notice %}}

Bên dưới là kiến trúc hạ tầng của ứng dụng web này.

![VPC](/images/3.serverless/3-1.png)

Khi nhìn vào kiến trúc hạ tầng này, bạn sẽ thấy chúng ta có một ứng dụng web ở phía bên trái. Nó đại diện cho ứng dụng để người dùng được sử dụng và trải nghiệm nó. Nó sẽ được truy cập bằng **Amazon CloudFront distribution.** Distribution này sẽ lấy resource của ứng dụng từ **Amazon S3 bucket.** Ứng dụng của chúng tôi truy cập vào các microservices của environment thông qua **API Gateway.** API Gateway này sẽ xử lí từng yêu cầu và route các traffic đến các chức năng thích hợp trong mỗi microservice của ứng dụng. Đối với ví dụ này, chúng ta đã có 2 e-commerce microservices, **Product và Orrder,** được cũng cấp các chức năng CRUD cơ bản. Mỗi service này sử dụng **Amazon DynamoDB** để lưu trữ và quản lí dữ liệu. Nhìn chung, kiến trúc hạ tầng này bao gồm tất cả các yếu tố cơ bản tạo thành một ứng dụng web serverless cơ bản. Tuy nhiên, ở giai đoạn này, solution này sẽ không hỗ trợ cho multi-tenant. Trong tương lai, chúng ta sẽ tìm hiểu và bổ sức các tính năng phục vụ cho multi-tenant.

#### Serverless microservices

Khái niệm về **microservice** có thể hơi khác một chút đối với **serverless environment.** Đúng là mỗi chứng năng có thể là microservice. Tuy nhiên, phổ biến hơn là có một tập hợp các functions đại diện cho một logical microservice. Trong trường hợp này, ranh giới microservice là API Gateway, được hỗ trợ bởi một hoặc nhiều Lambda functions. Như trong kiến trúc hạ tầng ở trên, Order service được chia thành nhiều functions như create, get, update và delete. Những functions này đều hoạt động trên cùng một dữ liệu và được nhóm lại với nhau thành một logical microservice.

Cuối cùng, chúng ta đã sử dụng Amazon DynamoDB để lưu trữ dữ liệu của mình và Amazon CloudWatch để lưu trữ tất cả các logs của ứng dụng.

### Nội dung

- [Deploy ứng dụng](3.1-deploy/)
- [Thêm data và tìm hiểu quy trình xử lí của architecture](3.2-adddata/)
- [Review code của ứng dụng](3.3-reviewcode/)
