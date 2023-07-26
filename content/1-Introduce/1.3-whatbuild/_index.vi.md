---
title: "Chúng ta sẽ xây dựng những cái gì?"
date: "`r Sys.Date()`"
weight: 3
chapter: false
pre: " <b> 1.3 </b> "
---

Trong buổi workshop này, chúng ta sẽ build cấu trúc chồng lên nhau bằng cách thêm dần các thành phần để đạt mục tiêu cuối cùng là xây dựng một ứng dụng SaaS với đầy đủ chức năng.

Dưới đây là kiến trúc mà chúng ta sẽ xây dựng trong buổi workshop này.

![VPC](/images/1.intro/1.3.png)

Chúng ta sẽ chia kiến trúc này thành 3 phần.

#### Web applications

Đây là 3 ứng dụng khác nhau mà chúng ta dùng nó để tương tác với các backend services. Mỗi ứng dụng đó đều được xây dựng bằng Angular.

- Ứng dụng **SaaS provider admin console** dành cho administrators của các nhà cung cấp SaaS
- Ứng dụng **Landing/sign-up application** dùng cho những tenants mới đăng ký thành viên.
- Ứng dụng **Sample SaaS commerce application** đại diện cho một ứng dụng thương mại điện tử điển hình. Người dùng cần phải đăng nhập vào để sử dụng các tính năng của nó.

#### Shared services

Bạn sẽ thấy một tập hợp các dịch vụ được chia sẻ, nó chịu trách nhiệm về việc quản lí người dùng, tenants ở các khía cạnh của ứng dụng. Cái tên **shared** chuyền tải khái niệm rằng các dịch vụ này là nền tảng cho môi trường SaaS, cung cấp các tính năng **cross-cutting** tách biệt với các application service của bạn và được chia sẻ với tất cả các tenants. Điều này có nghĩa là tất cả hoạt động và dữ liệu được dùng để tích hợp, quản lí, xác thực và cấu hình cho tenants đều được xử lí bởi share services.

{{% notice info %}}
Để tìm hiểu nhiều hơn về **Share Services,** [hãy xem tài liệu này](https://esj.com/articles/2009/04/15/saas-meaning.aspx?m=1), ở đây sẽ có phần Q&A để giải thích những khuất mắt của nó
{{% /notice %}}

#### Application services (Tiered Deployment Model)

Các application services là đại diện của các microservices, nó cung cấp các chức năng chính cho ứng dụng của bạn. Trong solution này, bạn sẽ thấy rằng chúng ta hỗ trợ mô hình triển khai theo tầng cho các microservices này. Các SaaS provider thường được yêu cầu hỗ trợ nhiều ties mà nó có những yêu cầu khác nhau về isolation, noisy neighbor, performance và những thứ khác. Ý tưởng ở đây là chúng ta sẽ xem xét cân nhắc sử dụng các tiers để hỗ trợ các yêu cầu này. Chúng ta sẽ sử dụng tenant tier để đóng góp vào cách triển khai các microservices cho một tenant nhất định.

Bạn sẽ thấy 3 tiers Basic, Standard, Premium mà tenants sẽ sử dụng mô hình pooled trong đó các tenants chia sẻ AWS resources. Mặt khác, Platinum tier tenants được triển khai với Silo model. Điều này nghĩa là mỗi Platinum tier tenant được hưởng AWS resources của iêng họ, không được chia sẻ với bất kì tenant nào khác.

{{% notice info %}}
Để tìm hiểu nhiều hơn về **Application Services,** [hãy xem tài liệu này](https://www.servicenow.com/workflows/creator-workflows/what-are-application-services.html), ở đây sẽ có phần Q&A để giải thích những khuất mắt của nó
{{% /notice %}}
