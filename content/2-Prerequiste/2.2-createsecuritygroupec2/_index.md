---
title : "Create Security Group for EC2"
date : "`r Sys.Date()`"
weight : 2
chapter : false
pre : " <b> 2.2 </b> "
---

#### Create VPC Security group for Amazon EC2

{{% notice note %}}
We will initialize and configure the Security group for the Amazon EC2 instance to use to connect the MySQL database at the DB instance and execute the application.
 {{% /notice %}}

1. In **VPC** interface
+ Select **Security Group**
+ Select **Create security group**

![securitygroupec2](/images/prerequiste/sg/SG-ec2-setup-0.png?featherlight=false&width=90pc)

2. Perform configuration
+ Security group name, enter **WebServer-SG**
+ Description, enter Security Group for Web Server
+ Select **VPC** created

![securitygroupec2](/images/prerequiste/sg/SG-ec2-setup-1.png?featherlight=false&width=90pc)

3. Configure **Inbound rules**
+ To add a rule, select **Add rule**
+ **SSH** port **22** used to connect to local machine. Source select **My IP**
+ **HTTP** port 80 and source is **Anywhere IPv4**
+ **HTTPS** port **443** and source is **Anywhere IPv4**
+ Select **Create security group**

![securitygroupec2](/images/prerequiste/sg/SG-ec2-setup-2.png?featherlight=false&width=90pc)