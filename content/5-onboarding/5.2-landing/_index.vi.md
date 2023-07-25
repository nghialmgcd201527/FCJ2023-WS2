---
title: "Sử dụng ứng dụng Sign-up dành cho tenant"
date: "`r Sys.Date()`"
weight: 2
chapter: false
pre: " <b> 5.2. </b> "
---

Các tenants cũng có thể onboard trong chế độ self-service. Đối với việc này, chúng ta cần một ứng dụng riêng đại diện cho công cụ hướng tới công chúng có thể được sử dụng để khách hàng tham với tư cách là một tenant.

{{% notice tip %}}
Nếu không may các bạn lỡ tắt trang terminal vừa chạy script, thì hãy vào lại thư mục `/environment/aws-serverless-saas-workshop/Lab2/scripts`, tiếp theo chạy câu lệnh `./geturl.sh` thì nó sẽ hiển thị lại URL mà các bạn cần
{{% /notice %}}

Ở bước [deploy lại ứng dụng sau khi thay đổi](/vi/4-saas/4.3-deploy/), chúng ta đã có URL của landing site. Chúng ta copy nó và paste vào trình duyệt để chạy nó. Bạn sẽ thấy giao diện như hình bên dưới. Đây là self-service page nơi mà bạn không cần bất kì thông tin xác thực nào để tiếp nhận một tenant.

![VPC](/images/4.5-landing/4.5-1.png)

Hãy click vào nút **Sign up now!** Sau đó bạn sẽ thấy một form như hình bên dưới. Đặt tên cho tenant là **tenant2,** chọn **Plan** là **Standard** và điền các thông tin còn lại trong form. Đảm bảo rằng cung cấp địa chỉ email mà bạn có thể truy cập. Bạn có thể cung cấp cùng địa chỉ email mà bạn đã sử dụng cho admin bằng cách thêm **+tenant2** vào hậu tố. Như email đã đăng kí cho admin trước đó là **lmnghia911@gmail.com** thì bây giờ sẽ điền email vào là **lmnghia911+tenant2@gmail.com.** Email này sẽ được sử dụng để cung cấp tenant admin user ở trong Amazon Cognito User Pool. Ngoài ra một nhóm Cognito User được tạo ra cho tenant mới này. Cognito sẽ gửi mail thông tin xác thực tạm thời cho người dùng tenant admin users. Nhấn nút **Submit** để bắt đầu quá trình.

![VPC](/images/4.5-landing/4.5-2.png)

Khi tenant được onboard thành công, bạn sẽ thấy có thông báo thành công hiện ra như hình bên dưới.

![VPC](/images/4.5-landing/4.5-3.png)

Quay lại ứng dụng SaaS admin, refresh lại page và click vào mục **Tenants** ở thanh điều hướng bên trái. Bạn sẽ thấy tenant mới xuất hiện ở đây.

![VPC](/images/4.5-landing/4.5-4.png)
