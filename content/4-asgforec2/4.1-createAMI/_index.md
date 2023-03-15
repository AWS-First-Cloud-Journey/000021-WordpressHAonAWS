---
title : "Initialize AMI from Webserver Instance"
date : "`r Sys.Date()`"
weight : 1
chapter : false
pre : " <b> 4.1 </b> "
---

1. Access to EC2
- Select Instances
- Select webserver-ec2
- Select Actions
- Select Image and templates
- Select Create image

![ami](/images/createautoscaling/AMI-setup-01.png?featherlight=false&width=90pc)

2. Configure Template
- Image name, enter webserver-AMI
- Image description, enter AMI for Webserver
- Select Create image

![ami](/images/createautoscaling/AMI-setup-02.png?featherlight=false&width=90pc)

3. AMI initialization takes about 5 minutes. After 5 minutes, we see the Status change to Available

![ami](/images/createautoscaling/AMI-setup-03.png?featherlight=false&width=90pc)