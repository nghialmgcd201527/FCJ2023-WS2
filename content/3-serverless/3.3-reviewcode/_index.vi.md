---
title: "Review code của ứng dụng"
date: "`r Sys.Date()`"
weight: 3
chapter: false
pre: " <b> 3.3. </b> "
---

Bây giờ chúng ta sẽ nhìn lại code đã được sử dụng để build và deploy architecture của chúng ta.

Quay lại IDE trên Cloud9 và mở thư mục **aws-serverless-saas-workshop.** Mở rộng thư mục **Lab1,** bạn sẽ thấy 2 thư mục con là **client** và **server.** Thư mục **client** gồm có code viết bằng Angular dành cho front end.

![VPC](/images/3.3-review/3.3-1.png)

Thư mục **server** chứa code dùng để deploy cơ sở hạ tầng AWS infrastructure. Bên trong thư mục server, bạn sẽ nhận thấy chúng ta có thư mục **OrderService và ProductService** đại diện cho product và order microservices. Cũng lưu ý file **template.yaml** sẽ đảm nhiệm việc deploy cơ sở hạ tầng. File này đang được triển khai bằng **Serverless Application Model (SAM),** nó là open-source framework dùng để build và deploy ứng dụng serverless. Trong thư mục **server** cũng có một thư mục tên là **layers,** nó chứa file **logger.py** được deploy bằng [Lambda Layers](https://aws.amazon.com/blogs/compute/using-lambda-layers-to-simplify-your-development-process/). Bây giờ tất cả các Lambda functions có thể share layer với nhau nhằm mục đích ghi lại các log theo cách centralized.

![VPC](/images/3.3-review/3.3-2.png)

Bây giờ bạn đã hiểu cơ bản về cấu trúc, tiếp tục thêm những thành phần cần thiết cho ứng dụng SaaS của chúng ta.
