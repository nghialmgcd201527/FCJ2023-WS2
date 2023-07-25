---
title: "AWS Serverless SaaS Workshop"
date: "`r Sys.Date()`"
weight: 1
chapter: false
---

# AWS Serverless SaaS Workshop

### Tổng quan

Trong bài workshop này, chúng ta sẽ xây dựng một solution **Software-as-a-Service (SaaS)** sử dụng các services **serverless** của AWS như **Amazon API Gateway, Amazon Cognito, AWS Lambda, Amazon DynamoDB và Amazon CloudWatch.** Mục tiêu của chúng ta là đưa đến cho các developers, architectures của SaaS đang làm việc với code có thể hiểu được cách thiết kế và chuyển sang sử dụng solution SaaS trên AWS.

Bài workshop này được viết dựa vào [SaaS Factory Serverless SaaS reference solution](https://github.com/aws-samples/aws-saas-factory-ref-solution-serverless-saas). Ở cuối buổi workshop này, bạn sẽ xây dược được ứng dụng SaaS với đầy đủ các chức năng của reference solution ở trên. Điều đáng chú ý trong buổi workshop này là các bạn không cần thiết phải hiểu **reference solution** trước đó. Bạn chỉ cần làm theo hướng dẫn, từng bước một và đọc kĩ những lời giải thích thì sẽ dễ hiểu và nắm được reference solution này.

Hình dưới đây là sơ đồ cấu trúc của [reference solution](https://github.com/aws-samples/aws-saas-factory-ref-solution-serverless-saas) trên.

![ConnectPrivate](/images/intro.png)

### Nội dung

1.  [Giới thiệu](1-introduce/)
2.  [Các bước chuẩn bị](2-prerequiste/)
3.  [Giới thiệu nhanh về ứng dụng web serverless](3-serverless/)
4.  [Giới thiệu SaaS shared services](4-saas/)
5.  [Bắt đầu ứng dụng](5-onboarding/)
6.  [Tổng kết](6-sum/)
7.  [Dọn dẹp tài nguyên](7-terminate/)
