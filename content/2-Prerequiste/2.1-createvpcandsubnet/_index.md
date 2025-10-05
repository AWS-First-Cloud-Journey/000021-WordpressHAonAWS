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


3. Options in **VPC Wizard**.
  + Select **VPC and more**
  + Enter **VPC** name: `Wordpress`
  + Enter **CIDR**: `192.168.0.0/16`
  

![VPC](/images/2.prerequisite/2.1.1.vpc.png)

4. **CIDR** options.
  + Choose the number of **public/private** subnets: 2
  + Public subnet 1: `192.168.1.0/24`
  + Public subnet 2: `192.168.2.0/24`
  + Private subnet 1: `192.168.3.0/24`
  + Private subnet 2: `192.168.4.0/24`

![VPC](/images/2.prerequisite/2.1.2.vpc.png)