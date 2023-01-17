---
title : "Chuẩn bị VPC và Subnet"
date :  "`r Sys.Date()`" 
weight : 1 
chapter : false
pre : " <b> 2.1 </b> "
---

#### Tạo VPC

1.	Truy cập **AWS Management Console**.
  +	Tìm **VPC**
  +	Chọn **VPC**

![VPC ](/images/prerequiste/vpc/VPC-setup-0.png?featherlight=false&width=90pc)

2.	Trong giao diện **VPC**.
  + Chọn **Your VPCs**
  + Chọn **Create VPC**

![VPC](/images/prerequiste/vpc/VPC-setup-1.png?featherlight=false&width=90pc)


3. Tuỳ chọn trong **VPC Wirard**.
  + Chọn **VPC and more**
  + Điền tên **VPC**
  + Nhập **CIDR**: 192.168.0.0/16
  + Chọn số lượng **public/private** subnet: 2

![VPC](/images/prerequiste/vpc/VPC-setup-2.png?featherlight=false&width=90pc)

4.	Tuỳ chọn **CIDR**.
  + public subnet 1: 192.168.1.0/24
  + public subnet 2: 192.168.2.0/24
  + private subnet 1: 192.168.3.0/24
  + private subnet 2: 192.168.4.0/24

![VPC](/images/prerequiste/vpc/VPC-setup-3.png?featherlight=false&width=90pc)