---
title: "Sử dụng ứng dụng SaaS admin"
date: "`r Sys.Date()`"
weight: 4
chapter: false
pre: " <b> 4.4. </b> "
---

Bây giờ các shared services của chúng ta đã được deploy, chúng ta có thể giới thiệu đến các tenants về ứng dụng của chúng ta. Solution này thực sự hỗ trợ hai luồng riêng biệt dành cho onboarding tenants. Cái đầu tiên chúng ta sẽ xem xét ở đây được trigger từ ứng dụng SaaS admin. Mô hình này thường được sử dụng trong các môi trường mà hệ thống không hỗ trợ **self-service onboarding model.**

#### Sử dụng ứng dụng SaaS admin

Đầu tiên, copy URL của ứng dụng SaaS Admin được gửi kèm trong email được gửi đến.

![VPC](/images/4.4-admin/4.4-1.png)

Paste URL đó và chạy trên trình duyệt của bạn. Bạn sẽ thấy trang login như hình dưới đây.

![VPC](/images/4.4-admin/4.4-2.png)

Trong quá trình deploy ứng dụng của chúng ta ở bước trước, bạn được cung cấp **username** và **password** trong email được gửi đến bạn. Bạn phải thiết lập lại password nếu bạn đăng nhập lần đầu tiên, username sẽ là **admin-user.**

![VPC](/images/4.4-admin/4.4-3.png)

Khi bạn đã đăng nhập thành công, nó sẽ hiển thị ra giao diện của ứng dụng trong trang Dashboard.

![VPC](/images/4.4-admin/4.4-4.png)

Ở thanh điều hướng bên trái, chọn mục **Tenants** nó sẽ hiển thị danh sách tenant đã onboarded nhiw hình dưới đây. Danh sách sẽ trống vì hiện tại chúng ta chưa có tenant nào onboard. Bây giờ, click vào nút **Add Tenant.**

![VPC](/images/4.4-admin/4.4-5.png)

Bạn sẽ thấy form cần điền thông tin như bên dưới. Đặt tên cho tenant là **test tenant 1,** đảm bảo cung cấp địa chỉ email mà bạn có thể truy cập. Bạn có thể cung cấp cùng địa chỉ email mà bạn đã sử dụng cho admin bằng cách thêm **+tenant1** vào hậu tốt. Như email đã đăng kí cho admin trước đó là **lmnghia911@gmail.com** thì bây giờ sẽ điền email vào là **lmnghia911+tenant1@gmail.com.** Email này sẽ được sử dụng để cung cấp tenant admin user ở trong Amazon Cognito User Pool. Ngoài ra một nhóm Cognito User được tạo ra cho tenant mới này. Cognito sẽ gửi mail thông tin xác thực tạm thời cho người dùng tenant admin users. Nhấn nút **Submit** để bắt đầu quá trình.
