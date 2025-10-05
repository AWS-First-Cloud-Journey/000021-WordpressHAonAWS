---
title : "Create Security Group for EC2"
weight : 2
date : "2025-10-02"
chapter : false
pre : " <b> 2.2 </b> "
---

#### Create VPC Security group for Amazon EC2

{{% notice note %}}
We will initialize and configure the Security group for the Amazon EC2 instance to use to connect the MySQL database at the DB instance and execute the application.
 {{% /notice %}}

1. In the **VPC** interface
    + Select **Security Group**
    + Select **Create security group**

![securitygroupec2](/images/2.prerequisite/2.2.0.sg.png)

2. Proceed with configuration
    + **Security group name**, enter `WebServer-SG`
    + **Description**, enter `Security Group for Database Instance`
    + Select the created **VPC**

![securitygroupec2](/images/2.prerequisite/2.2.1.sg.png)

3. Configure **Inbound rules**
    + To add a rule, select **Add rule**
    + **SSH** port **22** used to connect to local machine. Source select **My IP**
    + **HTTP** port 80 and source is **Anywhere IPv4**
    + **HTTPS** port **443** and source is **Anywhere IPv4**
    + Select **Create security group**

![securitygroupec2](/images/2.prerequisite/2.2.2.sg.png)