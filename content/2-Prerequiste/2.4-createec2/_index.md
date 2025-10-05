---
title : "Initiating EC2 Instance"
weight : 4
date : "2025-10-02"
chapter : false
pre : " <b> 2.4 </b> "
---

{{% notice note %}}
We perform **Amazon EC2** initialization in **Public subnet** for the purpose of connecting **MySQL databas**e of **DB instance** in **Private subnet**
{{% /notice %}}

1. Access **AWS Management Console**
    - Find **EC2**
    - Select **EC2**

![ec2](/images/createec2/EC2-setup-0.png?featherlight=false&width=90pc)

2.	In the **EC2** interface
    -	Select **Instance**
    -	Select **launch Instance**

![ec2](/images/2.prerequisite/2.4.1.ec2.png)

3. In the **Launch an instance** interface
    -	**Name**, enter `webserver-ec2`
    -	**AMI** select **Amazon linux**

![ec2](/images/2.prerequisite/2.4.0.ec2.png)

4. Proceed to select **Instance type** and select **Create new key pair**
    -	**Instance type** select **t2.micro**
    -	Key pair select **create new key pair**

![ec2](/images/2.prerequisite/2.4.2.ec2.png)

5. In the **Create key pair** interface
    -	Key pair name, enter `webserver-keypair`
    -	Key pair type, select **RSA**
    -	Private key file format, select **.pem**
    -	Select **Create key pair**

![ec2](/images/2.prerequisite/2.4.3.ec2.png)

6. Configure **Network** for instance
    -	**VPC** select the **VPC** created for the lab
    -	Select **public subnet**
    -	**Auto-assign public IP**, select **Enable**
    -	Select **existing security group**
    -	Select **WebServer-SG**

![ec2](/images/2.prerequisite/2.4.4.ec2.png)

7. Proceed to **Create Instance** from the previous settings
    -	In the **Summary** interface select **Launch Instance**

![ec2](/images/2.prerequisite/2.4.5.ec2.png)

8.	Complete **EC2** initialization, select **View all instances** to see details

![ec2](/images/2.prerequisite/2.4.6.ec2.png)

9.	This **EC2 instance** will be used to connect to the **DB instance** and deploy the **Wordpress** application

![ec2](/images/2.prerequisite/2.4.7.ec2.png)