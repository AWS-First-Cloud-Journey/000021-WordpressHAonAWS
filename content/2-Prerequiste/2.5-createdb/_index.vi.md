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

1. Truy cập **AWS Management Console**:

    - Tìm **RDS**.
    - Chọn **Aurora and RDS**

![db](/images/2.prerequisite/2.5.0.rds.png)

2.	Trong giao diện **Amazon RDS**:

    -	Chọn **Create Database**.

![db](/images/2.prerequisite/2.5.1.rds.png)


3. Tiến hành cấu hình:

    -	Chọn **Standard create**.
    -	Trong Engine options, chọn **MySQL**.
    -	Chọn version **SQL** thích hợp với **Wordpress** (version 8.0.42).

![db](/images/2.prerequisite/2.5.2.rds.png)


4. Trong phần Template:

    -	Chọn **Production** sẽ được sử dụng **Availability** and **durability** (có thể chọn **Multi-AZ DB cluster** hoặc **Multi-AZ DB instance** hoặc **Single-AZ DB instance**). Trong bài lab sử dụng **Multi-AZ DB instance** không hỗ trợ **Multi-AZ DB cluster snapshot**.

![db](/images/2.prerequisite/2.5.3.rds.png)



{{% notice tip %}}
Đối với trường hợp triển khai trên môi trường Dev/Test (hoặc Production) bạn nên lựa chọn Multi-AZ deployment để tạo thêm một standby instance ở AZ khác phục vụ cho mục tiêu dự phòng.
{{% /notice %}}



5. Cấu hình thông tin về **Database**:

    -	**DB instance identifier**, nhập `wordpress-db`.
    -	**Master username**, nhập `admin`.
    -   **Credentials** chọn **Self managed**
    -	**Master password**, nhập password của bạn. Ví dụ bài lab: `dbpassword`.
    -	**Confirm password**, nhập lại password.

![db](/images/2.prerequisite/2.5.4.rds.png)


6. Cấu hình **Conectivity** để mặc định:

    -	**Compute Resource**, chọn **Don't connect to an EC2 compute resource**
    -	**VPC**, chọn VPC dành cho bài lab đã tạo
    -	**Subnet group**, chọn **Create new DB subnet Group**
    -	**Public access**, chọn **No**
    -	Đối với **VPC Security group**, chọn **Choose existing**
    -	Chọn **DB instance SG**

![db](/images/2.prerequisite/2.5.5.rds.png)

7. Cấu hình **Additional configuration**

    -	**Initial database name**, nhập `awsuser`
    -	Các mục còn lại để mặc định

![db](/images/2.prerequisite/2.5.6.rds.png)


8. Xem lại ước tính giá tiền:

![db](/images/2.prerequisite/2.5.7.rds.png)


9. Đợi khoảng 10 phút sau, hoàn thành tạo **DB instance** và **Status** của DB instance chuyển sang **Available**

![db](/images/2.prerequisite/2.5.8.rds.png)


10. Trong giao diện **DB instance** vừa tạo

-	Chọn **Connectivity & security**
-	Lưu trữ **Enpoint & port** của **DB instance** để thực hiện cấu hình các bước tiếp theo.

![db](/images/2.prerequisite/2.5.9.rds.png)