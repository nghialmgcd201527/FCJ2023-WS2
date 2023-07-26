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

Chúng ta cùng deploy ứng dụng serverless bằng cách file script **deployment.sh** trong thư mục `/environment/aws-serverless-saas-workshop/Lab1/scripts`, cùng chạy câu lẹnh dưới đây trong terminal của Cloud9.

```
1| cd ~/environment/aws-serverless-saas-workshop/Lab1/scripts/

2| ./deployment.sh -s -c --stack-name serverless-saas-workshop-lab1
```

Chúng ta sẽ đợi khoảng từ 5 đến 8 phút để script chạy hoàn thành. Ở trong câu lệnh ở trên, các parameters **-c** và **-s** ở đây biểu thị rằng chúng ta đang deploy cả code của server và client side. Sau khi chạy script hoàn thành, nó sẽ hiển thị URL của ứng dụng như hình.

![VPC](/images/3.1-deploy/3.1-1.png)

{{% notice tip %}}
Nếu không may các bạn lỡ tắt trang terminal vừa chạy script, thì hãy vào lại thư mục `/environment/aws-serverless-saas-workshop/Lab1/scripts`, tiếp theo chạy câu lệnh `./geturl.sh <stack_name>`. **<stack_name>** ở đây là tên của stack mà bạn đã tạo ra khi chạy script ở trên.
{{% /notice %}}

#### Kiểm tra stack vừa được tạo trong CloudFormation

Nhập **CloudFormation** ở thanh tìm kiếm service trên AWS Console sau đó chọn **CloudFormation**.

![VPC](/images/3.1-deploy/3.1-2edit.png)

Ở thanh điều hướng bên trái, chúng ta chọn **Stacks.** Ở đây sẽ hiển thị danh sách các stacks và chúng ta sẽ thấy stack của chúng ta có tên là **serverless-saas-workshop-lab1** vừa được tạo.

![VPC](/images/3.1-deploy/3.1-3edit.png)

#### Kiểm tra S3 bucket vừa được tạo

Nhập **S3** ở thanh tìm kiếm service trên AWS Console sau đó chọn **S3**.

![VPC](/images/3.1-deploy/3.1-4edit.png)

Chúng ta sẽ thấy có hai S3 buckets vừa được tạo ra để lưu trữ resource của ứng dụng chúng ta.

![VPC](/images/3.1-deploy/3.1-5edit.png)

#### Chạy thử URL của ứng dụng

Coppy URL của ứng dụng và paste nó vào trình duyệt bạn đang sử dụng, bạn sẽ thấy giao diện như hình dưới đây.

![VPC](/images/3.1-deploy/3.1-6.png)

Vậy là chúng ta đã thành công việc deploy ứng dụng serverless của chúng ta. Trong bước tiếp theo,chúng ta sẽ thêm data vào ứng dụng và khám phá cấu trúc hoạt động của nó.
