---
title: "Tăng dung lượng của Cloud9 instance"
date: "`r Sys.Date()`"
weight: 2
chapter: false
pre: " <b> 2.2 </b> "
---

{{% notice tip %}}
Đầu tiên, chúng ta sẽ cập nhật phiên bản mới nhất của AWS CLI:

```
pip install --user --upgrade awscli aws-sam-cli

```

{{% /notice %}}

Ở trang terminal trên Cloud9, chạy command sau để để clone Git repository **aws-serverless-saas-workshop**:

```
git clone https://github.com/aws-samples/aws-serverless-saas-workshop.git

```

Sau khi chạy câu lệnh trên, chúng ta sẽ được như hình. Chúng ta sẽ thấy thư mục **aws-serverless-saas-workshop** được tạo ra.

![VPC](/images/2.prerequisite/2.2-repodisk/2.2-1edit.png)

#### Kiểm tra dung lượng của Cloud9 instance

{{% notice info %}}
Mặc định, dung lượng trống của một Cloud9 instance chỉ tầm khoảng 2GB. Dùng đoạn script dưới đây để tránh tình trạng hết dung lượng và vấn đề trong suốt buổi workshop.
{{% /notice %}}

Chuyển đến thư mục **aws-serverless-saas-workshop,** kiểm tra dung lượng của volume hiện tại bằng lệnh sau:

```
cd aws-serverless-saas-workshop
df -h

```

Chúng ta sẽ nhận được kết quả như hình bên dưới:

![VPC](/images/2.prerequisite/2.2-repodisk/2.2-2edit.png)

filesystem ở đường dẫn /dev/nvme0n1p1 là volume mà chúng ta đang sử dụng. Chúng ta sẽ thấy dung lượng trống của Cloud9 instance này là 3.6G. Để tránh tình trạng hết dung lượng trong suốt buổi workshop, chúng ta được yêu cầu tối thiểu 50G cho workshop này, bắt đầu tăng dung lượng của Cloud9 instance này lên 50G.

Các bạn hãy vào thư mục **Cloud9Setup** và mở file script **increase-disk-size.sh** bằng đường dẫn sau:

```
cd ~/environment/aws-serverless-saas-workshop/Cloud9Setup/
```

Sau khi mở file script **increase-disk-size.sh,** chúng ta sẽ thấy nội dung đoạn script dùng để tăng dung lượng:

![VPC](/images/2.prerequisite/2.2-repodisk/2.2-3.png)

Chúng ta tăng dung lượng Cloud9 instance bằng cách chạy file script đó:

```
./increase-disk-size.sh

```

Sau khi tăng thành công, chúng ta sẽ nhận được output như hình:

![VPC](/images/2.prerequisite/2.2-repodisk/2.2-4.png)

Bây giờ hãy kiểm tra lại dung lượng hiện tại bằng lệnh sau:

```
df -h

```

Và chúng ta sẽ thấy kết quả.

![VPC](/images/2.prerequisite/2.2-repodisk/2.2-5edit.png)

Như chúng ta thấy ở đường dẫn /dev/nvme0n1p1, dung lượng hiện tại của Cloud9 instance đã tăng lên 50G.

{{% notice note %}}
Thỉnh thoảng, mặc dù dung lượng của Cloud9 instance đã được tăng lên 50G, nó vẫn có thể hiển thị là 10G khi bạn chạy câu lệnh `df -h`. Trong trường hợp này, hãy restart Cloud9 instance bằng câu lệnh `sudo reboot` và chạy lại câu lệnh `df -h` để kiểm tra lại.
{{% /notice %}}
