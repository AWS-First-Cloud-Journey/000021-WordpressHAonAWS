---
title : "Preparing VPC and Subnet"
weight : 1
date : "2025-10-02"
chapter : false
pre : " <b> 2.1 </b> "
---

#### Create VPC

1. Go to **AWS Management Console**.
  + Find **VPC**
  + Select **VPC**

![VPC ](/images/prerequiste/vpc/VPC-setup-0.png?featherlight=false&width=90pc)

2. In the **VPC** interface.
  + Select **Your VPCs**
  + Select **Create VPC**

![VPC](/images/prerequiste/vpc/VPC-setup-1.png?featherlight=false&width=90pc)


3. Options in **VPC Wirard**.
  + Select **VPC and more**
  + Enter the name **VPC**
  + Enter **CIDR**: 192.168.0.0/16
  + Choose the number of **public/private** subnets: 2

![VPC](static/images/2.prerequisite/2.1.1.vpc.png)

4. **CIDR** option.
  + public subnet 1: 192.168.1.0/24
  + public subnet 2: 192.168.2.0/24
  + private subnet 1: 192.168.3.0/24
  + private subnet 2: 192.168.4.0/24

![VPC](/images/prerequiste/vpc/VPC-setup-3.png?featherlight=false&width=90pc)