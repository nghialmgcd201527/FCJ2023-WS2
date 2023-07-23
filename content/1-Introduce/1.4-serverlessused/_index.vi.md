---
title: "Những service Serverless được sử dụng"
date: "`r Sys.Date()`"
weight: 4
chapter: false
pre: " <b> 1.4 </b> "
---

Dưới đây là danh sách các AWS services và tính năng mà buổi workshop này sử dụng:

- [AWS Serverless Application Model (SAM)](https://aws.amazon.com/serverless/sam/) là một open-source framework để xây dựng các ứng dụng serverless. Nó cung cấp các syntax ngắn để thực hiện các chức năng, APIs, cơ sở dữ liệu và event source mappings. Chỉ với một vài dòng trên mỗi resource, bạn có thể định nghĩa được ứng dụng mà mình muốn và mô hình sử dụng YAML. Trong suốt quá trình deployment, SAM biến đổi và mở rộng cú pháp thành AWS CloudFormation cho phép bạn xây dựng các ứng dụng serverless nhanh hơn.

- [AWS Cloud Development Kit (CDK)](https://aws.amazon.com/cdk/) là open-source software development framework để định nghĩa các cloud infrastructure dưới dạng code và provision nó bằng AWS CloudFormation. Nó cho phép bạn sử dụng các ngôn ngữ lập trình như TypeScript, JavaScript, Python, Java, C#/.Net để định nghĩa các AWS resources trong một ứng dụng. CDK sẽ biến đổi các ngôn ngữ lập trình này thành CloudFormation template và deploy nó lên AWS.

- [Amazon API Gateway](https://aws.amazon.com/api-gateway/) là một fully managed service để tạo, quản lí, monitor và bảo mật các API ở bất kì quy mô nào. Nó cung cấp các tính năng như API creation, publishing, maintenance, monitoring, và securing. Nó cũng cho phép bạn tạo các RESTful APIs và WebSocket APIs để truyền tải dữ liệu ở bất kì quy mô nào.

  - [REST APIs](https://aws.amazon.com/what-is/restful-api/) là một dạng API mà nó sử dụng HTTP requests để truyền tải dữ liệu. REST APIs có thể truyền tải dữ liệu ở bất kì định dạng nào như JSON, XML, HTML, text, etc.
  - [Lambda Authorizer](https://docs.aws.amazon.com/apigateway/latest/developerguide/apigateway-use-lambda-authorizer.html) là một cách để bảo mật các REST APIs bằng cách sử dụng Lambda function để xác thực các yêu cầu API. Lambda authorizers có thể được sử dụng để xác thực các yêu cầu API bằng cách sử dụng bearer token, request parameters, headers, và client certificates.
  - [Usage Plans](https://docs.aws.amazon.com/apigateway/latest/developerguide/api-gateway-api-usage-plans.html) là một cách để quản lí các yêu cầu API của bạn. Nó cho phép bạn quản lí các yêu cầu API bằng cách sử dụng API keys và rate limits.
  - [API keys](https://docs.aws.amazon.com/apigateway/latest/developerguide/api-gateway-setup-api-key-with-console.html) là một cách để bảo mật các REST APIs bằng cách sử dụng API keys. API keys có thể được sử dụng để bảo mật các REST APIs bằng cách sử dụng các API keys.

- [Amazon Cognito](https://aws.amazon.com/cognito/) là một fully managed service để xác thực, quản lí người dùng và đồng bộ hóa dữ liệu người dùng trên các thiết bị. Nó cung cấp các tính năng như sign-up, sign-in, và access control cho các ứng dụng web và mobile. Nó cũng cho phép bạn đồng bộ hóa dữ liệu người dùng trên các thiết bị.

  - [User Pools](https://docs.aws.amazon.com/cognito/latest/developerguide/cognito-user-identity-pools.html) là một cách để xác thực và quản lí người dùng. Nó cung cấp các tính năng như sign-up, sign-in, và access control cho các ứng dụng web và mobile.

- [AWS Lambda](https://aws.amazon.com/lambda/) là một service serverless compute cho phép bạn chạy code mà không cần phải provision hay manage các servers. Lambda cung cấp một cách để chạy code mà không cần phải quản lí các servers. Nó cũng cung cấp các tính năng như auto scaling, high availability, và native integrations với một số service khác của AWS.

- [Amazon DynamoDB](https://aws.amazon.com/dynamodb/) là một cặp key-value serverless và là một loại cơ sở dữ liệu phi quan hệ (Non-SQL) mang lại hiệu suất một phần nghìn giây ở mọi quy mô. Tương tự với những cơ sở dữ liệu khác, Amazon DynamoDB sẽ lưu trữ data bằng các bảng. Trong ứng dụng của chúng ta, chúng ta sẽ lưu trữ thông tin của các tasks trong bảng của DynamoDB. Bảng này sẽ được truy cập bằng Lambda function bằng sự phản hồi đến API từ ứng dụng web của chúng ta.

Thêm vào đó, chúng ta sẽ lựa chọn và sử dụng ngôn ngữ lập trình chính là Python trong buổi workshop này.
