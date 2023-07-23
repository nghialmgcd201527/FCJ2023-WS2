---
title: "Các bước chuẩn bị"
date: "`r Sys.Date()`"
weight: 2
chapter: false
pre: " <b> 2. </b> "
---

Bạn có thể deploy ứng dụng của bạn từ môi trường làm việc local nếu bạn muốn nhưng tôi khuyến khích bạn sử dụng **AWS Cloud9 integrated development environment (IDE).**

{{% notice warning %}}
Hãy nhớ rằng Cloud9 workspace chỉ nên được tạo ra bởi IAM user (hoặc là được gán vào một IAM role thích hợp) với đặc quyền của Admin, không được dùng root user.
{{% /notice %}}

#### **Cloud9 Workspace**

Chúng ta thường dùng môi trường phát triển tích hợp (Integrated Development Environment - IDE) ở local, trong bài workshop này, chúng ta sẽ dùng Cloud9. Nó là một IDE chạy trên cloud sử dụng trình duyệt, bao gồm những tính năng quan trọng, thiết yếu ở local IDE mà chúng ta thường dùng như viết, chạy, debug code. Cloud9 đã được trang bị sẵn những gói tệp tin như JavaScript, Python, NodeJS và những thứ khác [ở đây](https://aws.amazon.com/cloud9/)

> Để các dịch vụ của AWS phản hồi nhanh hơn, hãy chọn Region gần nhất trong suốt buổi workshop.

### Nội dung

- [Tạo Cloud9 Workspace](2.1-createcloud9workspace/)
- [Cài đặt Amplify CLI](2.2-installamplifycli/)
