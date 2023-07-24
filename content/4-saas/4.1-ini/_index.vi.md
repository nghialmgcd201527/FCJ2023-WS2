---
title: "Khởi tạo dự án"
date: "`r Sys.Date()`"
weight: 1
chapter: false
pre: " <b> 4.1. </b> "
---

Ở bước trước, chúng ta đã tìm hiểu cấu trúc và cách deploy ứng dụng serverless với SAM template [ở đây](/vi/3-serverless/)

Ở bước này, chúng ta sẽ khởi tạo dự án trước khi đi tìm hiểu chi tiết về cấu trúc của nó. Chúng ta hãy chạy lệnh dưới đây để khởi tạo dự án. Hãy chuyền giá trị địa chỉ email, nó sẽ được sử dụng để nhận thông tin dùng để đăng nhập vào ứng dụng của admin.

```
cd ~/environment/aws-serverless-saas-workshop/Lab2/scripts/

./deployment.sh -s -c --email <email address>
```

{{% notice info %}}
Hãy đi đến bước tiếp theo trong lúc đoạn script đang được thực thi. Nhấn nút **Next.**
{{% /notice %}}

File script sẽ gửi thông tin đăng nhập cho admin vào địa chỉ email mà bạn đã cung cấp ở trên.

![VPC](/images/4.1-ini/4.1-1.png)

Khi file script thực thi thành công, chúng ta sẽ nhận được hai đường dẫn **Admin site URL** và **Landing site URL** như hình bên dưới.

![VPC](/images/4.1-ini/4.1-2.png)

Chúng ta coppy và paste URL của **Admin site.** Nhập vào **username** và **password** được gửi đến email của chúng ta để đăng nhập.

{{% notice info %}}
Ở bước hệ thống yêu cầu chúng ta reset lại password, để password chúng ta được validate, các bạn hãy bao gồm chữ in hoa và một kí tự đặc biệt.
{{% /notice %}}

Giao diện ứng dụng dành cho admin sẽ như hình dưới đây.

![VPC](/images/4.1-ini/4.1-3.png)

Và giao diện của **landing site** sẽ như hình dưới đây.

![VPC](/images/4.1-ini/4.1-4.png)
