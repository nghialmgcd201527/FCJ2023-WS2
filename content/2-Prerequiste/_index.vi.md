---
title: "Các bước chuẩn bị"
date: "`r Sys.Date()`"
weight: 2
chapter: false
pre: " <b> 2. </b> "
---

#### API Gateway - REST API

Ở bước này, bạn có thể sử dụng Amazon API Gateway console để create và test một simple REST API với tích hợp HTTP cho website của bạn.

Ví dụ với website PeetStore, API sẽ hỗ trợ các phương thức cho client truy cập vào phía backend của website **http://petstore-demo-endpoint.execute-api.com/petstore/pets.**

- **GET / :** cho phép truy cập và đọc dữ liệu từ resource gốc của API. API Gateway sẽ phản hồi với một dữ liệu có sẵn trong cửa hàng.
- **GET /pests :** cho phép truy cập và đọc dữ liệu từ resource của API **/pets** được tích hợp với tên phụ trợ **/pets.** Backend trả về cho page những pets có sẵn trong store. Đây là ví dụ khi tích hợp với HTTP, URL có tên như này `http://petstore-demo-endpoint.execute-api.com/petstore/pets`.
- **POST /pets :** cho phép truy cập và thêm dữ liệu vào resource của API **/pets** được tích hợp với tên phụ trợ **/petstore/pets.** Khi nhận được yêu cầu chính xác, backend sẽ thêm pets chính xác vào PetStore và trả kết quả về với caller. Nó cũng được tích hợp vs HTTP.

API hỗ trợ truy cập CORS thông qua các phương thức tùy chọn của loại tích hợp có tên là **MOCK.** API Gateways trả về các headers hỗ trợ truy cập CORS. Chúng tôi sẽ hướng dẫn bạn các bước để tạo và kiểm tra API từ ví dụ ở trên sử dụng API Gateway Console.

#### **Cloud9 Workspace**

Bạn có thể deploy ứng dụng của bạn từ môi trường làm việc local nếu bạn muốn nhưng tôi khuyến khích bạn sử dụng **AWS Cloud9 integrated development environment (IDE).**

{{% notice warning %}}
Hãy nhớ rằng Cloud9 workspace chỉ nên được tạo ra bởi IAM user (hoặc là được gán vào một IAM role thích hợp) với đặc quyền của Admin, không được dùng root user.
{{% /notice %}}

Chúng ta thường dùng môi trường phát triển tích hợp (Integrated Development Environment - IDE) ở local, trong bài workshop này, chúng ta sẽ dùng Cloud9. Nó là một IDE chạy trên cloud sử dụng trình duyệt, bao gồm những tính năng quan trọng, thiết yếu ở local IDE mà chúng ta thường dùng như viết, chạy, debug code. Cloud9 đã được trang bị sẵn những gói tệp tin như JavaScript, Python, NodeJS và những thứ khác [ở đây](https://aws.amazon.com/cloud9/)

> Để các dịch vụ của AWS phản hồi nhanh hơn, hãy chọn Region gần nhất trong suốt buổi workshop.

### Nội dung

- [Tạo Cloud9 Workspace](2.1-createcloud9workspace/)
- [Tăng dung lượng của Cloud9 instance](2.2-repodisk/)
- [Cài đặt các công cụ cần thiết](2.3-installtool/)
- [Thiết lập role ARN của CloudWatch log cho API Gateway](2.4-cloudwatch/)
