---
title : "Tạo Security Group cho Database Instance"
date :  "`r Sys.Date()`" 
weight : 3 
chapter : false
pre : " <b> 2.3 </b> "
---

#### Tạo VPC Security group cho Amazon EC2

{{% notice note %}}
Chúng ta sẽ khởi tạo và cấu hình Security group cho Amazon RDS Database instance sử dụng để lưu trữ CDSL và cho phép truy xuất dữ liệu qua cổng 3306.
 {{% /notice %}}

1. Trong giao diện **VPC**
+ Chọn **Security Group**
+ Chọn **Create security group**

![securitygroupec2](/images/prerequiste/sg/SG-db-setup-0.png?featherlight=false&width=90pc)

2. Tiến hành cấu hình
+ **Security group name**, nhập **Database-SG**
+ **Description**, nhập **Security Group for Database Instance**
+ Chọn **VPC** đã tạo

![securitygroupec2](/images/prerequiste/sg/SG-db-setup-1.png?featherlight=false&width=90pc)

3. Cấu hình **Inbound rules**
+	Chọn **MYSQL/Aurora** cổng **3306** và custon source là **WebServer-SG**
+	Chọn **Create security group**

![securitygroupec2](/images/prerequiste/sg/SG-db-setup-2.png?featherlight=false&width=90pc)