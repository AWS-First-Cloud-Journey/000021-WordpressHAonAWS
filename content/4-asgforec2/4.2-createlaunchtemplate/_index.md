---
title : "Launch Template"
date : "2025-10-02"
weight : 2
chapter : false
pre : " <b> 4.2 </b> "
---


In this section, you will create a Launch Template using the AMI you created from the Amazon Linux 2 Instance in the previous step.
1. Access to EC2
- Select Launch Templates
- Select Create launch template

![ami](/images/createautoscaling/launch-template-setup-01.png?featherlight=false&width=90pc)

2. In Create launch template interface
- Launch template name, enter Webserver-ASG-template
- Template version description, enter Template for Webserver ASG

![ami](/images/createautoscaling/launch-template-setup-02.png?featherlight=false&width=90pc)

3. Perform AMI . selection
- Select My AMIs
- Select Owned by me
- Select webserver-AMI

![ami](/images/createautoscaling/launch-template-setup-03.png?featherlight=false&width=90pc)

4. Make Instance type selection
- Select t2.micro
- Key pair, select asg-keypair created when creating EC2 instance.

![ami](/images/createautoscaling/launch-template-setup-04.png?featherlight=false&width=90pc)

5. Perform Network Configuration
- Subnet, select public subnet
- Firewall (Security Group), select Select existing security group
- Select Webserver-SG

![ami](/images/createautoscaling/launch-template-setup-05.png?featherlight=false&width=90pc)

6. Check and execute Create launch template

![ami](/images/createautoscaling/launch-template-setup-06.png?featherlight=false&width=90pc)

7. Execute successfully and select View launch templates

![ami](/images/createautoscaling/launch-template-setup-07.png?featherlight=false&width=90pc)

8. View the template just created.

![ami](/images/createautoscaling/launch-template-setup-08.png?featherlight=false&width=90pc)