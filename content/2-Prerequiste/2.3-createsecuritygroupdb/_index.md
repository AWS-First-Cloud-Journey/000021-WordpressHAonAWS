---
title : "Create Security Group for Database Instance"
date : "`r Sys.Date()`"
weight : 3
chapter : false
pre : " <b> 2.3 </b> "
---

#### Create VPC Security group for Amazon EC2

{{% notice note %}}
We will create and configure a Security group for the Amazon RDS Database instance to use to host the CDSL and allow data access over port 3306.
 {{% /notice %}}

1. In **VPC** interface
+ Select **Security Group**
+ Select **Create security group**

![securitygroupec2](/images/prerequiste/sg/SG-db-setup-0.png?featherlight=false&width=90pc)

2. Perform configuration
+ **Security group name**, enter **Database-SG**
+ **Description**, enter **Security Group for Database Instance**
+ Select **VPC** created

![securitygroupec2](/images/prerequiste/sg/SG-db-setup-1.png?featherlight=false&width=90pc)

3. Configure **Inbound rules**
+ Select **MYSQL/Aurora** port **3306** and custon source is **WebServer-SG**
+ Select **Create security group**

![securitygroupec2](/images/prerequiste/sg/SG-db-setup-2.png?featherlight=false&width=90pc)