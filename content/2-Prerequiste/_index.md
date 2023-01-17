---
title : "Các bước chuẩn bị"
date :  "`r Sys.Date()`" 
weight : 2 
chapter : false
pre : " <b> 2. </b> "
---

{{% notice note %}}
Trong bước chuẩn bị chúng ta sẽ tiến hành tạo **VPC** và **Subnet** cho web application hoạt động  
Tạo 2 SG cho **EC2 instance** và **DB instance**
{{% /notice %}}

Để tìm hiểu cách tạo các EC2 instance và VPC với public/private subnet các bạn có thể tham khảo bài lab :
  - [Làm việc với Amazon VPC](https://000003.awsstudygroup.com/vi/)
  - [Giới thiệu về Amazon EC2](https://000004.awsstudygroup.com/vi/)
  - [Giới thiệu về Amazon Database](https://000005.awsstudygroup.com/vi/)



### Nội dung
  - [Chuẩn bị VPC và Subnet](2.1-createvpcandsubnet/)
  - [Tạo Security Group cho EC2](2.2-createsecuritygroupec2/)
  - [Tạo Security Group cho Database Instance](2.3-createsecuritygroupdb/)
  - [Khởi tạo EC2 Instance](2.4-createec2/)
  - [Khởi tạo Database Instance](2.5-createdb/)