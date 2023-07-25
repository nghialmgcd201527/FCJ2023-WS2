---
title: "Dọn dẹp tài nguyên"
date: "`r Sys.Date()`"
weight: 7
chapter: false
pre: " <b> 7. </b> "
---

#### Cloud9 instance

Chúng ta vào **Cloud9 Console** bằng cách nhập **Cloud9** ở thanh tìm kiếm service trên AWS Console sau đó chọn **Cloud9**. Chọn Cloud9 mà bạn đã tạo [ở bước 2.1](/vi/2-prerequiste/2.1-createcloud9workspace) và nhấn nút **Delete** ở góc trên bên phải.

![VPC](/images/7.terminate/7-1.png)

Sau đó nhập **Delete** để chúng ta confirm việc xóa Cloud9 instance này và nhấn nút **Delete.** Chờ vài phút để Cloud9 instance được xóa hoàn toàn.

![VPC](/images/7.terminate/7-2.png)

#### CloudFormation

Chúng ta vào **CloudFormation Console** bằng cách nhập **CloudFormation** ở thanh tìm kiếm service trên AWS Console sau đó chọn **CloudFormation**. Chúng ta sẽ thấy list các stack được tạo ra trong bài workshop này. Chúng ta chọn từng cái và nhấn nút **Delete** ở góc trên bên phải.

![VPC](/images/7.terminate/7-3.png)

Đối với những **nested stack,** sau khi nhấn nút **Delete,** chúng ta sẽ chọn option **Delete nested stack** và nhập **delete** để confirm. Cuối cùng, chúng ta nhấn nút **Delete.**

![VPC](/images/7.terminate/7-4.png)

Chờ khoảng vài phút, vậy là chúng ta đã xóa tất cả stacks trong CloudFormation.

#### S3 Bucket

Chúng ta vào **S3 Console** bằng cách nhập **S3** ở thanh tìm kiếm service trên AWS Console sau đó chọn **S3**. Chúng ta sẽ thấy list các buckets được tạo ra trong bài workshop này. Chúng ta chọn từng cái và nhấn nút **Delete** ở góc trên bên phải.

![VPC](/images/7.terminate/7-5.png)

Nếu chúng ta nhận được thông báo như hình thì hãy click vào **empty bucket configuration** để làm trống bucket trước khi xóa nó.

![VPC](/images/7.terminate/7-6.png)

Cuối cùng, chúng ta cần nhập **permanently delete** để confirm việc làm trống bucket và nhấn nút **Empty.** Sau khi làm trống bucket, chúng ta quay lại trang danh sách buckets, chọn một bucket nhấn nút **Delete** để xóa bucket. Vậy là chúng ta đã xóa thành công S3 bucket.

#### CloudWatch Log Groups

Chúng ta vào **CloudWatch Log Groups** bằng cách nhập **CloudWatch** ở thanh tìm kiếm service trên AWS Console sau đó chọn **CloudWatch**. Ở thanh điều hướng bên trái, chúng ta chọn **Log groups,** nó sẽ hiện ra danh sách tất cả các log groups được tạo trong workshop này. Chúng ta chọn tất cả các log groups được tạo trong workshop này, sau đó nhấn nút **Action,** chọn **Delete log group(s)** và nhấn nút **Delete.** Vậy là chúng ta đã xóa thành công Chúng ta sẽ thấy list các stack được tạo ra trong bài workshop này. Chúng ta chọn từng cái và nhấn nút **Delete** ở góc trên bên phải.

![VPC](/images/7.terminate/7-7.png)

Vậy là chúng ta đã xóa tất cả các tài nguyên được tạo ra trong bài workshop này.
