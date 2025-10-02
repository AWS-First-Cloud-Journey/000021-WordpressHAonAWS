---
title : "Tạo Security Group cho EC2"
weight : 2 
date : "2025-10-02"
chapter : false
pre : " <b> 2.2 </b> "
---

#### Tạo VPC Security group cho Amazon EC2

{{% notice note %}}
Chúng ta sẽ khởi tạo và cấu hình Security group cho Amazon EC2 instance sử dụng để kết nối MySQL database ở DB instance và thực thi ứng dụng.
 {{% /notice %}}

1. Trong giao diện **VPC**
+ Chọn **Security Group**
+ Chọn **Create security group**

![securitygroupec2](/images/2.prerequisite/2.2.0.sg.png)

2. Tiến hành cấu hình
+ **Security group name**, nhập `WebServer-SG`
+ **Description**, nhập `Security Group for Database Instance`
+ Chọn **VPC** đã tạo

![securitygroupec2](/images/2.prerequisite/2.2.1.sg.png)

3. Cấu hình **Inbound rules**
+ Để thêm rule, chọn **Add rule**
+ **SSH** cổng **22** dùng để kết nối với máy local. Source chọn **My IP**
+ **HTTP** cổng 80 và source là **Anywhere IPv4**
+ **HTTPS** cổng **443** và source là **Anywhere IPv4**
+ Chọn **Create security group**

![securitygroupec2](/images/2.prerequisite/2.2.2.sg.png)