---
title : "Khởi tạo Database Instance"
weight : 5 
date : "2025-10-02"
chapter : false
pre : " <b> 2.5 </b> "
---

{{% notice note %}}
Chúng ta thực hiện khởi tạo **Database Instance** ở **Private subnet** với mục đích kết nối bảo vệ **DB Instance** chỉ cho **EC2 Web server** truy cập.
{{% /notice %}}

1. Truy cập **AWS Management Console**
- Tìm **RDS**
- Chọn **RDS**

![db](/images/createdatabase/db-setup-0.png?featherlight=false&width=90pc)

2.	Trong giao diện **Amazon RDS**
-	Chọn **Create Database**

![db](/images/createdatabase/db-setup-1.png?featherlight=false&width=90pc)

3. Tiến hành cấu hình
-	Chọn **Standard create**
-	Trong Engine options, chọn **MySQL**
-	Chọn version **SQL** thích hợp với **Wordpress** (version 5.7)


![db](/images/createdatabase/db-setup-2.png?featherlight=false&width=90pc)

4. Trong phần Template
-	Chọn **Production** sẽ được sử dụng **Availability** and **durability** (có thể chọn **Multi-AZ DB instance** hoặc **Multi-AZ DB Cluster** hoặc **Single DB instance**). Trong bài lab sử dụng **Multi-AZ DB instance** không hỗ trợ **Multi-AZ DB cluster snapshot**
-	Trong Engine options, chọn MySQL.

![db](/images/createdatabase/db-setup-3.png?featherlight=false&width=90pc)

{{% notice note %}}
Nếu chọn Free tier sẽ không sử dụng Availability and durability, không chọn được loại Deployment
{{% /notice %}}

{{% notice tip %}}
Đối với trường hợp triển khai trên môi trường Dev/Test (hoặc Production) bạn nên lựa chọn Multi-AZ deployment để tạo thêm một standby instance ở AZ khác phục vụ cho mục tiêu dự phòng.
{{% /notice %}}



5. Cấu hình thông tin về **Database**
-	**DB instance identifier**, nhập **wordpress-db**
-	**Master username**, nhập **admin**
-	**Master password**, nhập password của bạn. Ví dụ bài lab: dbpassword
-	**Confirm password**, nhập lại password.

![db](/images/createdatabase/db-setup-4.png?featherlight=false&width=90pc)

6. Cấu hình Instance và Storage để mặc định

![db](/images/createdatabase/db-setup-5.png?featherlight=false&width=90pc)

7. Cấu hình Network cho DB instance
-	**Network type**, chọn **IPv4**
-	**VPC**, chọn VPC dành cho bài lab đã tạo
-	**Subnet group**, chọn **Create new DB subnet Group**
-	**Public access**, chọn **No**
-	Đối với **VPC Security group**, chọn **Choose existing**
-	Chọn **DB instance SG**

![db](/images/createdatabase/db-setup-6.png?featherlight=false&width=90pc)

8. Cấu hình database
-	**Initial database name**, nhập **awsuser**
-	Các mục còn lại để mặc định

![db](/images/createdatabase/db-setup-7.png?featherlight=false&width=90pc)

9. Đợi khoảng 10 phút sau, hoàn thành tạo DB instance và Status của DB instance chuyển sang Available

![db](/images/createdatabase/db-setup-8.png?featherlight=false&width=90pc)

10. Trong giao diện **DB instance** vừa tạo
-	Chọn **Connectivity & security**
-	Lưu trữ **Enpoint & port** của **DB instance** để thực hiện cấu hình các bước tiếp theo.

![db](/images/createdatabase/db-setup-9.png?featherlight=false&width=90pc)