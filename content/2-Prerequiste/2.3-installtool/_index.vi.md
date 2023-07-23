---
title: "Cài đặt các công cụ cần thiết"
date: "`r Sys.Date()`"
weight: 3
chapter: false
pre: " <b> 2.3 </b> "
---

{{% notice tip %}}
Đầu tiên, chúng ta sẽ cập nhật phiên bản mới nhất của AWS CLI:

```
pip install --user --upgrade awscli aws-sam-cli

```

{{% /notice %}}

Các bạn hãy vào thư mục **Cloud9Setup** và mở file script **pre-requisites.sh** bằng đường dẫn sau:

```
cd ~/environment/aws-serverless-saas-workshop/Cloud9Setup/
```

Sau khi mở file script **pre-requisites.sh,** chúng ta sẽ thấy nội dung đoạn script dùng để cài đặt toàn bộ các công cụ cần thiết của buổi workshop này:

![VPC](/images/2.prerequisite/2.3-install/2.3-1.png)

Chúng ta chạy file script đó để cài đặt, sẽ mất khoảng từ 3 đến 5 phút để hoàn thành:

```
./pre-requisites.sh

```

Đoạn script trên sẽ tải và upgrade các công cụ cho Cloud9 IDE của bạn:

- **Python 3.8**
- **AWS CLI**
- **AWS SAM**
- **AWS CDK CLI**
- **git-remote-codecommit**
- **Node and npm**

Sau khi chạy script hoàn thành, chúng ta sẽ thấy kết quả như hình bên dưới:

![VPC](/images/2.prerequisite/2.3-install/2.3-2.png)

Tiếp theo, vẫn trong đường dẫn đó, chúng ta mở file **pre-requisites-versions-check.sh :**

![VPC](/images/2.prerequisite/2.3-install/2.3-3.png)

Đoạn script trên sẽ kiểm tra phiên bản của các công cụ đã được cài đặt ở trên có phù hợp với buổi workshop này hay không. Chúng ta chạy file script đó để kiểm tra:

```
./pre-requisites-versions-check.sh
```

Hãy chắn rằng kết quả của bạn sẽ nhận được **PASS** cho tất cả các công cụ được cài đặt và cập nhật:

![VPC](/images/2.prerequisite/2.3-install/2.3-4.png)

{{% notice note %}}
Thỉnh thoảng, mặc dù đã cài đặt và cập nhật đúng phiên bản nhưng khi chạy script kiểm tra phiên bản nhưng mà nó vẫn chưa cập nhật thì các bạn hãy restart lại Cloud9 instance bằng câu lệnh `sudo reboot` và chạy lại script kiểm tra phiên bản đó.
{{% /notice %}}
