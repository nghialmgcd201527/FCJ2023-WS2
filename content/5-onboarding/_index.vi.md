---
title: "Bắt đầu ứng dụng"
date: "`r Sys.Date()`"
weight: 5
chapter: false
pre: " <b> 5. </b> "
---

Bây giờ các shared services của chúng ta đã được deploy, chúng ta có thể giới thiệu đến các tenants về ứng dụng của chúng ta. Solution này thực sự hỗ trợ hai luồng riêng biệt dành cho onboarding tenants. Cái đầu tiên chúng ta sẽ xem xét ở đây được trigger từ ứng dụng SaaS admin. Mô hình này thường được sử dụng trong các môi trường mà hệ thống không hỗ trợ **self-service onboarding model.**

Các tenants cũng có thể onboard trong chế độ self-service. Đối với việc này, chúng ta cần một ứng dụng riêng đại diện cho công cụ hướng tới công chúng có thể được sử dụng để khách hàng tham với tư cách là một tenant.

### Nội dung

- [Sử dụng ứng dụng SaaS admin](5.1-onboardingadmin/)
- [Sử dụng ứng dụng Sign-up dành cho tenant](5.2-landing/)
- [Review dữ liệu được lưu trữ](5.3-data/)
