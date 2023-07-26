---
title: "Thiết lập role ARN của CloudWatch log cho API Gateway"
date: "`r Sys.Date()`"
weight: 4
chapter: false
pre: " <b> 2.4 </b> "
---

{{% notice tip %}}
Đầu tiên, chúng ta sẽ cập nhật phiên bản mới nhất của AWS CLI:

```
pip install --user --upgrade awscli aws-sam-cli

```

{{% /notice %}}

Ở bước này, trong account AWS của chúng ta, chúng ta sẽ đảm bảo role ARN của CloudWatch log được thiết lập cho API Gateway. Bạn cần bước thiết lập này để chắc chắn API Gateway có thể ghi log vào CloudWatch để có thể debug errors của API Gateway REST APIs.

#### API Gateway - REST API

Nhập **API Gateway** ở thanh tìm kiếm service trên AWS Console sau đó chọn **API Gateway**.

![Name for Cloud9 Workspace và chọn Environment type](/images/2.prerequisite/2.4-cloudwatch/2.4-1edit.png)

Nếu đây là lần đầu bạn sử dụng API Gateway, bạn sẽ thấy trang giới thiệu các tính năng của API Gateway. Dưới **REST API,** ta chọn **Build.** Khi popup **Create Example API** xuất hiện, ta chọn **OK.**

Nếu như đây không phải là lần đầu sử dụng API Gateway, ta chọn **Create API** ở góc trên bên phải của trang.

![Name for Cloud9 Workspace và chọn Environment type](/images/2.prerequisite/2.4-cloudwatch/2.4-2edit.png)

Ở trang **Choose an API type,** ta chọn loại **REST API** nhưng không phải **Private** và chọn **Build.**

![Name for Cloud9 Workspace và chọn Environment type](/images/2.prerequisite/2.4-cloudwatch/2.4-3edit.png)

Ở trang **Choose the protocol,** chúng ta sẽ chọn giao thức của nó, chúng ta chọn **REST**, ở phần **Create new API,** chúng ta chọn **Example API,** nó sẽ hiện ra một example API, chúng ta có thể xem chi tiết về nó.

![Name for Cloud9 Workspace và chọn Environment type](/images/2.prerequisite/2.4-cloudwatch/2.4-4edit.png)

Và cuối cùng là nhấn nút **Import,** nó sẽ tạo ra API mới.

![Name for Cloud9 Workspace và chọn Environment type](/images/2.prerequisite/2.4-cloudwatch/2.4-5edit.png)

API mới sẽ được hiển thị ở đây với cái tên là **PetStore.**

![Name for Cloud9 Workspace và chọn Environment type](/images/2.prerequisite/2.4-cloudwatch/2.4-6edit.png)

{{% notice tip %}}
Để biết thêm về cách sử dụng API đó, các bạn sẽ xem ở đây: [Example REST API](https://docs.aws.amazon.com/apigateway/latest/developerguide/api-gateway-create-api-from-example.html)

{{% /notice %}}

#### Tạo CloudWatch role

Bước tiếp theo, chúng ta sẽ tạo role ARN cho phép CloudWatch ghi lại log của cách hành động gửi yêu cầu đến API.

Đầu tiên chúng ta sẽ vào [AWS Identity and Access Management (IAM) console](https://ap-southeast-1.console.aws.amazon.com/iamv2/home?region=ap-southeast-1#/home), ở thanh điều hướng bên trái, chúng ta chọn **Roles.**

![Name for Cloud9 Workspace và chọn Environment type](/images/2.prerequisite/2.4-cloudwatch/2.4-7edit.png)

Click vào nút **Create role.**

![Name for Cloud9 Workspace và chọn Environment type](/images/2.prerequisite/2.4-cloudwatch/2.4-8edit.png)

Ở trang **Create role,** phần **Trusted entity type,** chúng ta chọn **AWS service,** ở phần **Use case,** chúng ta sẽ click vào drop box **Use cases for other AWS services,** chúng ta chọn **API Gateway** và nhần nút **Next.**

![Name for Cloud9 Workspace và chọn Environment type](/images/2.prerequisite/2.4-cloudwatch/2.4-9edit.png)

Ở trang **Add permissions,** chúng ta sẽ thấy policy **AmazonAPIGatewayPushToCloudWatchLogs** đã được chọn sẵn. Policy này có tất cả các quyền chúng ta cần.

![Name for Cloud9 Workspace và chọn Environment type](/images/2.prerequisite/2.4-cloudwatch/2.4-10edit.png)

Cuối cùng ở trang **Name, review, and create,** chúng ta đặt tên cho nó ở phần **Role name,** ở đây mình sẽ đặt là **cloudwatch-api.** Những mục khác chúng ta để mặt định, nhấn nút **Create role.** Vậy là chúng ta đã tạo thành công.

![Name for Cloud9 Workspace và chọn Environment type](/images/2.prerequisite/2.4-cloudwatch/2.4-11edit.png)

Quay trở lại trang **Role,** nhập vào thanh tìm kiếm **cloudwatch-api** nó sẽ hiện thị role mình vừa tạo.

![Name for Cloud9 Workspace và chọn Environment type](/images/2.prerequisite/2.4-cloudwatch/2.4-12edit.png)

Chúng ta click vào role **cloudwatch-api** để xem chi tiết. Chúng ta sẽ thấy giá trị **ARN** của role đó và coppy nó để dùng cho bước tiếp theo.

![Name for Cloud9 Workspace và chọn Environment type](/images/2.prerequisite/2.4-cloudwatch/2.4-13edit.png)

Quay trở lại trang [API Gateway console](https://ap-southeast-1.console.aws.amazon.com/apigateway/main?region=ap-southeast-1), chọn API có tên là **PetStore** sau đó ở thanh điều hướng bên trái, ở dưới **Client Certificates,** chúng ta chọn **Settings.** Ở phần **CloudWatch log role ARN,** chúng ta paste ARN của role **cloudwatch-api** vào và nhấn nút **Save.**

![Name for Cloud9 Workspace và chọn Environment type](/images/2.prerequisite/2.4-cloudwatch/2.4-14edit.png)

Vậy là chúng ta đã hoàn thành việc thiếp lập CloudWatch log role ARN cho API Gateway. Hãy cùng đi đến bước tiếp theo.
