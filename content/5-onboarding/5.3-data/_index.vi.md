---
title: "Review dữ liệu được lưu trữ"
date: "`r Sys.Date()`"
weight: 3
chapter: false
pre: " <b> 5.3. </b> "
---

Để hiểu thêm về những gì xảy ra trong quá trình registration, cùng nhìn lại dữ liệu của tenants và users được lưu trữ.

#### Cognito User pools

Đầu tiên, chúng ta đã nói trước đó, buổi workshop này sử dụng **Amazon Cognito** để lưu trữ thông tin chi tiết của user. Hãy cùng xem lại user pools được tạo ra trong **Amazon Cognito.**

Nhập **Cognito** ở thanh tìm kiếm service trên AWS Console sau đó chọn **Cognito.**

![VPC](/images/4.6-data/4.6-1.png)

Sau đó bên thanh điều hướng bên trái, chúng ta chọn **User pools.** Chúng ta sẽ thấy các **User pool name** được tạo ra trong buổi workshop của chúng ta sau khi script được deploy hoàn thành. **OperationUsers-ServerlessSaaSUserPool** được dùng để lưu trữ những users SaaS admin và **PooledTenant-ServerlessSaaSUserPool** được dùng để lưu trữ thông tin của user được tạo ra trong quá trình đăng kí.

![VPC](/images/4.6-data/4.6-2.png)

Chúng ta chọn **PooledTenant-ServerlessSaaSUserPool.** Click vào **Users** tab để xem các users có sẵn.

![VPC](/images/4.6-data/4.6-3.png)

Tiếp theo, chúng ta click vào **Groups** tab để xem các groups dã có sẵn.

![VPC](/images/4.6-data/4.6-4.png)

Quay trở lại tab **Users,** click vào bất kì một trong những tenant admin vừa được tạo và để ý đến thuộc tính **tenantId** và **custom role** được thêm vào user này. Những thuộc tính custom này cho phép chúng ta tạo ràng buộc giữa user và tenant. Bất cứ khi nào người dùng xác thực, token được trả về sẽ bao gồm các thuộc tính custom này, cho phép dễ dàng truy cập vào context của tenant trên hệ thống. Context này sẽ đóng vai trò quan trọng trong việc triển khai phần vùng dữ liệu và tenant isolation trong bài workshop này.

![VPC](/images/4.6-data/4.6-5.png)

#### DynamoDB

Nhập **DynamoDB** ở thanh tìm kiếm service trên AWS Console sau đó chọn **DynamoDB.**

![VPC](/images/4.6-data/4.6-6.png)

Ở thanh điều hướng bên trái, chúng ta chọn **Tables.** Nó sẽ hiện thị danh sách các table đã được tạo ở trong bước trước. Chúng ta chọn **ServerlessSaaS-TenantDetails.**

![VPC](/images/4.6-data/4.6-7.png)

Tiếp theo, chúng ta sẽ click vào nút **Explore table items** để xem các items được lưu trữ trong table. Ở phần **Items returned,** chúng ta sẽ thấy có 2 object được tạo ra trước đó có trong danh sách này.

![VPC](/images/4.6-data/4.6-8.png)
