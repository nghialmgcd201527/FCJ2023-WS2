---
title: "Deploy ứng dụng"
date: "`r Sys.Date()`"
weight: 1
chapter: false
pre: " <b> 3.1. </b> "
---

{{% notice info %}}
Ở bước trước, bạn đã được cung cấp tài liệu để tìm hiểu cấu trúc và cách deploy ứng dụng serverless với SAM template [tại đây](https://catalog.us-east-1.prod.workshops.aws/workshops/841ce16b-9d86-48ac-a3f6-6a1b29f95d2b/en-US/step-1). Trong bài này chúng ta sẽ bỏ qua chi tiết những bước đó và chỉ cần chạy file script.
{{% /notice %}}

Chúng ta cùng deploy ứng dụng serverless bằng cách chạy câu lẹnh dưới đây trong terminal của Cloud9.

```
cd ~/environment/aws-serverless-saas-workshop/Lab1/scripts/
./deployment.sh -s -c --stack-name serverless-saas-workshop-lab1
```

Chúng ta sẽ đợi khoảng từ 5 đến 8 phút để script chạy hoàn thành. Ở trong câu lệnh ở trên, các parameters **-c** và **-s** ở đây biểu thị rằng chúng ta đang deploy cả code của server và client side. Sau khi chạy script hoàn thành, nó sẽ hiển thị URL của ứng dụng như hình.

![VPC](/images/3.serverlessbackend/3.1-dynamodb/3.1-1.png)
