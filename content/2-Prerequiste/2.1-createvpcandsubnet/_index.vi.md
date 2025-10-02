---
title : "Chuẩn bị VPC và Subnet"
weight : 1 
date : "2025-10-02"
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
  

![VPC](/images/2.prerequisite/2.1.1.vpc.png)

4.	Tuỳ chọn **CIDR**.
  + Chọn số lượng **public/private** subnet: 2
  + Public subnet 1: 192.168.1.0/24
  + Public subnet 2: 192.168.2.0/24
  + Private subnet 1: 192.168.3.0/24
  + Private subnet 2: 192.168.4.0/24

![VPC](/images/2.prerequisite/2.1.2.vpc.png)