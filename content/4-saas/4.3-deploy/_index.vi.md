---
title: "Deploy cập nhật những thay đổi"
date: "`r Sys.Date()`"
weight: 3
chapter: false
pre: " <b> 4.3. </b> "
---

{{% notice note %}}
Hãy chắc chắn bạn đã lưu lại tất cả sự thay đổi từ bước trước đó.
{{% /notice %}}

Đến lúc này, việc khởi tạo dự án đã hoàn thành, nếu nó chưa chạy xong thì hãy đợi nó hoàn thành trước khi tiếp tục. Nếu quan tâm, hãy thoải mái khám phá các đoạn code bên trong foler **TenantManagementService,** nơi bạn chưa xem ở bước trước đó.

Chạy câu lệnh dưới đây để deploy đoạn code mới mà bạn vừa thêm vào ở trong các file trước đó. Hãy lưu ý, trong file script **deploy-updates.sh** bạn sẽ thấy bạn đang sử dụng câu lệnh **sam sync** để đồng bộ code đã cập nhật thay vì deploy lại tất cả stack lại.

![VPC](/images/4.3-deploy2/4.3-1.png)

Chạy câu lệnh dưới đây.

```
cd ~/environment/aws-serverless-saas-workshop/Lab2/scripts

./deploy-updates.sh
```

Sau khi deploy lại thành công, chúng ta sẽ nhận lại được URL của **Admin site** và **Landing site** như hình dưới đây.

![VPC](/images/4.3-deploy2/4.3-2.png)
