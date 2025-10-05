---
title : "Launch Template"
date : "2025-10-02"
weight : 2
chapter : false
pre : " <b> 4.2 </b> "
---


In this section, you will create a Launch Template using the AMI you created from the Amazon Linux 2 Instance in the previous step.
1. Access **EC2**:
    -	Select **Launch Templates**
    -	Select **Create launch template**

![ami](/images/createautoscaling/launch-template-setup-01.png?featherlight=false&width=90pc)

2. In the **Create launch template** interface:
    -	**Launch template name**, enter `Webserver-ASG-template`
    -	**Template version description**, enter `Template for Webserver ASG`

![launch](/images/4.s3/4.2.lt.png)

3. Perform **AMI** selection
    -	Select My **AMIs**
    -	Select **Owned by me**
    -	Select **webserver-AMI**

![launch](/images/4.s3/4.2.1.lt.png)

4. Perform **Instance type** selection
    -	Select **t2.micro**
    -	Key pair, select webserver-keypair created when creating EC2 instance.

![launch](/images/4.s3/4.2.3.png)

5. Perform **Network** configuration
    -	Subnet, select **public subnet**.
    -	**Firewall (Security Group)**, select **Select existing security group**.
    -	Select **Webserver-SG**.

![launch](/images/4.s3/4.2.4.png)

6. Review and perform Create launch template

![ami](/images/createautoscaling/launch-template-setup-06.png?featherlight=false&width=90pc)

7. Execute successfully and select View launch templates

![ami](/images/createautoscaling/launch-template-setup-07.png?featherlight=false&width=90pc)