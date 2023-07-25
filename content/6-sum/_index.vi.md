---
title: "Tổng kết"
date: "`r Sys.Date()`"
weight: 6
chapter: false
pre: " <b> 6. </b> "
---

Trong buổi workshop này, chúng ta đã giới thiệu các khái niệm về các shared services và giới thiệu một số tenant trong pooled model. Chúng ta cũng đã thấy cách thông tin người dùng và tenant được lưu trữ bên trong Cognito và DynamoDB. Nhưng ở giai đoạn này, các product và order microservices không có cơ chế để theo dõi tenant nào đang cố truy cập hệ thống và thậm chí cách phân vùng dữ liệu theo dịch vụ kinh doanh bởi tenants.
