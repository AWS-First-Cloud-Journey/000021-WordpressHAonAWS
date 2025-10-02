---
title : "Khởi tạo EC2 Instance"
weight : 4 
date : "2025-10-02"
chapter : false
pre : " <b> 2.4 </b> "
---

{{% notice note %}}
Chúng ta thực hiện khởi tạo **Amazon EC2** ở **Public subnet** với mục đích kết nối **MySQL databas**e của **DB instance** trong **Private subnet**
{{% /notice %}}

1. Truy cập **AWS Management Console**
    - Tìm **EC2**
    - Chọn **EC2**

![ec2](/images/createec2/EC2-setup-0.png?featherlight=false&width=90pc)

2.	Trong giao diện **EC2**
    -	Chọn **Instance**
    -	Chọn **launch Instance**

![ec2](/images/2.prerequisite/2.4.1.ec2.png)

3. Trong giao diện **Launch an instance**
    -	**Name**, nhập `webserver-ec2`
    -	**AMI** chọn **Amazon linux**

![ec2](/images/2.prerequisite/2.4.0.ec2.png)

4. Tiến hành chọn **Instance type** và chọn **Create new key pair**
    -	**Instance type** chọn **t2.micro**
    -	Key pair chọn **create new key pair**

![ec2](/images/2.prerequisite/2.4.2.ec2.png)

5. Trong giao diện **Create key pair**
    -	Key pair name, nhập `webserver-keypair`
    -	Key pair type, chọn **RSA**
    -	Private key file format, chọn **.pem**
    -	Chọn **Create key pair**

![ec2](/images/2.prerequisite/2.4.3.ec2.png)

6. Cấu hình **Network** cho instance
    -	**VPC** chọn **VPC** tạo cho bài lab
    -	Chọn **public subnet**
    -	**Auto-assign public IP**, chọn **Enable**
    -	Chọn Select **existing security group**
    -	Chọn **WebServer-SG**

![ec2](/images/2.prerequisite/2.4.4.ec2.png)

7. Tiến hành **Create Instanc**e từ các setting trước đó
    -	Trong giao diện **Summary** chọn **Launch Instance**

![ec2](/images/2.prerequisite/2.4.5.ec2.png)

8.	Hoàn thành khởi tạo **EC2**, chọn **View all instances** để xem chi tiết

![ec2](/images/2.prerequisite/2.4.6.ec2.png)

9.	**EC2 instance** này sẽ sử dụng để kết nối với **DB instance** và triển khai ứng dụng **Wordpress**

![ec2](/images/2.prerequisite/2.4.7.ec2.png)