---
title: "Thêm data và tìm hiểu quy trình xử lí của architecture"
date: "`r Sys.Date()`"
weight: 2
chapter: false
pre: " <b> 3.2. </b> "
---

Đầu tiên chúng ta sẽ đi đến API Gateway Console, nhập **API Gateway** ở thanh tìm kiếm service trên AWS Console sau đó chọn **API Gateway**.

![VPC](/images/3.2-data/3.2-1.png)

Nó sẽ đưa chúng ta đến trang danh sách các APIs đã được tạo. Chúng ta sẽ thấy có một API có tên là **serverless-saas-workshop-lab1** được tạo ra từ file script **deployment.sh** ở bước trước.

![VPC](/images/3.2-data/3.2-2.png)

Coppy ID của API này. Click vào tên của API đó để xem chi tiết cách chúng ta đã tích hợp API Gateway với Lambda functions. Bạn có thể nhìn thấy bằng cách click vào các methods khác nhau như POST, GET, PUT và sẽ thấy mỗi methods được liên kết với Lamba function của nó. Cách này cho phép bạn mở rộng quy mô từng Lambda một cách độc lập mà không ảnh hưởng đến các Lambda functions khác.

Như hình dưới đây, chúng ta click vào method POST nó sẽ ra quy trình hoạt động của method này.

![VPC](/images/3.2-data/3.2-3.png)

Tiếp theo chúng ta sẽ add product vào hệ thống sử dụng API do API Gateway cung cấp. Quay trở lại Cloud9 terminal, coppy câu lệnh dưới đây, lệnh này sẽ đưa ra lệnh gọi POST REST tới API và thêm một product mới vào hệ thống. Chúng ta sẽ thay **<api-id>** và **<region>** bằng giá trị ID của API lúc nãy vừa coppy và region chúng ta đang hoạt động.

```
curl -X POST https://<api-id>.execute-api.<region>.amazonaws.com/prod/product -H 'Content-Type: application/json'  -d '{"category": "category1", "name": "Lamborghini", "price": "1000", "sku": "dollar"}'
```

Chúng ta sẽ thấy như hình:

![VPC](/images/3.2-data/3.2-4.png)

Bây giờ, cùng kiểm tra lại bảng Amazon DynamoDB và xem dữ liệu đã được thêm vào sau khi lệnh ở trên đã được thực thi thành công.

Nhập **DynamoDB** ở thanh tìm kiếm service trên AWS Console sau đó chọn **DynamoDB**.

![VPC](/images/3.2-data/3.2-5.png)

Ở thanh điều hướng bên trái, chúng ta chọn **Tables.** Ở đây sẽ hiển thị danh sách các tables và chúng ta sẽ thấy tất cả tables được tạo ra là **Order-Lab1** và **Product-Lab1.**

![VPC](/images/3.2-data/3.2-6.png)

Click vào table **Product-Lab1,** sau đó click vào **Explore table items** ở phía bên phải. Để xem các dữ liệu trong bảng.

![VPC](/images/3.2-data/3.2-7.png)

Và chúng ta sẽ thấy dữ liệu mà chúng ta vừa thêm vào sau khi chạy câu lệnh trên ở phần **Items returned.**

![VPC](/images/3.2-data/3.2-8.png)

Cuối cùng, chúng ta sẽ kiểm tra ở CloudWatch để xem các logs được tạo ra khi gọi API. Nhập **CloudWatch** ở thanh tìm kiếm service trên AWS Console sau đó chọn **DynamoDB**.

![VPC](/images/3.2-data/3.2-9.png)

Ở thanh điều hướng bên trái, chúng ta chọn **Log groups** trong phần **Logs.** Và chọn log group có tên bao gồm cụm từ **CreateProductFunction.**

![VPC](/images/3.2-data/3.2-10.png)

Sau đó chúng ta xuống dưới phần **Log streams,** click vào log stream vừa được tạo ra khi gọi API.

![VPC](/images/3.2-data/3.2-11.png)

Cuối cùng, chúng ta sẽ chọn **Timestamp** mà ở đó nó sẽ gồm dữ liệu chúng ta thêm vào khi gọi API.

![VPC](/images/3.2-data/3.2-12.png)

Khi các bạn thấy như hình, vậy là chúng ta đã thành công khi thêm data vào hệ thống và nhận các logs về hoạt động này.
