---
title : "Initialize AMI from Webserver Instance"
date : "2025-10-02"
weight : 1
chapter : false
pre : " <b> 4.1 </b> "
---

1. Access EC2
    -	Select **Instances**
    -	Select **webserver-ec2**
    -	Select **Actions**
    -	Select **Image and templates**
    -	Select **Create image**

![wp](/images/4.s3/4.1.ami.png)

2. Configure Template
    -	Image name, enter `webserver-AMI`
    -	Image description, enter `AMI for Webserver`
    -	Select **Create image**

![wp](/images/4.s3/4.2.ami.png)

3. The AMI initialization process takes about 5 minutes. After 5 minutes, we see the Status change to **Available**

![wp](/images/4.s3/4.3.ami.png)