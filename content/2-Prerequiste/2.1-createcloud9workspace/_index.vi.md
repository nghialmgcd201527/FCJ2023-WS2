---
title: "Tạo Cloud9 Workspace"
date: "`r Sys.Date()`"
weight: 1
chapter: false
pre: " <b> 2.1 </b> "
---

#### Khởi tạo Cloud9

1. Nhập **Cloud9** ở thanh tìm kiếm service trên AWS Console sau đó chọn **Cloud9**.

![Name for Cloud9 Workspace và chọn Environment type](/images/2.prerequisite/2.1-createcloud9workspace/2.1-1edit.png)

2. Chọn **Create environment**

![Name for Cloud9 Workspace và chọn Environment type](/images/2.prerequisite/2.1-createcloud9workspace/2.1-2edit.png)

3. Đặt tên cho Cloud9 Workspace là **saas-workshop.**
4. Ở mục **Description** hãy nhập mục đích bạn muốn sử dụng trong workspace này. Nhập **Saas workshop with serverless**
5. **Environment type,** ở đây chúng ta sẽ tạo một server để chạy Cloud9 workspace này. Mình sẽ chọn option **New EC2 instance** để tạo một server mới.

![Name for Cloud9 Workspace và chọn Environment type](/images/2.prerequisite/2.1-createcloud9workspace/2.1-3edit.png)

6. Sang phần setting cho **New EC2 instance,** chọn **Additional instance types** sau đó chúng ta chọn loại **t3.large.**

![Setting cho new EC2 instance](/images/2.prerequisite/2.1-createcloud9workspace/2.1-4edit.png)

7. Giữ nguyên mặc định cho những thiết lập khác. Click nút **Create.**

![Keep default](/images/2.prerequisite/2.1-createcloud9workspace/2.1-5edit.png)

8. Đợi khoảng 10 phút để Cloud9 Workspace được tạo. Khi Cloud9 Workspace được tạo xong, chúng ta sẽ có một môi trường để làm việc với AWS CLI và các công cụ khác. Trong danh sách các **Environments** được tạo ra, hãy tìm environment **serverless-workshop** và click vào nút **Open** để mở môi trường Cloud9.

![VPC](/images/2.prerequisite/2.1-createcloud9workspace/2.1-6edit.png)

10. Sau khi môi trường mở ra, chúng ta hãy tắt những phần bên dưới đã được khởi tạo lúc bắt đầu và tạo một **trang terminal** mới.

{{% notice warning %}}
Hãy chắc chắn rằng bạn đã tắt tất cả các tab đã tổn tại khi chúng ta mở Cloud9 IDE trước khi chúng ta thực hiện một hoạt đồng nào đó, hãy click vào **X** button để tắt tab đó. Cái này rất cần thiết để đảm bảo rằng bước tiếp theo khi cài đặt những công cụ cần thiết cho workshop này sẽ không bị ảnh hưởng.
{{% /notice %}}

![VPC](/images/2.prerequisite/2.1-createcloud9workspace/2.1-7edit.png)

Workspace của chúng ta sẽ trông như thế này.

![VPC](/images/2.prerequisite/2.1-createcloud9workspace/2.1-8new.png)
