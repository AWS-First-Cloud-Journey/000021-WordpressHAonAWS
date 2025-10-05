---
title : "Create Security Group for Database Instance"
weight : 3
date : "2025-10-02"
chapter : false
pre : " <b> 2.3 </b> "
---

#### Create VPC Security group for Amazon EC2

{{% notice note %}}
We will create and configure a Security group for the Amazon RDS Database instance to use to host the CDSL and allow data access over port 3306.
 {{% /notice %}}

1. In the **VPC** interface
    + Select **Security Group**
    + Select **Create security group**

![securitygroupec2](/images/2.prerequisite/2.2.0.sg.png)

2. Proceed with configuration
    + **Security group name**, enter `Database-SG`
    + **Description**, enter `Security Group for Database Instance`
    + Select the created **VPC**

![securitygroupec2](/images/2.prerequisite/2.3.1.sg.png)

3. Configure **Inbound rules**
    +	Select **MYSQL/Aurora** port **3306** and custom source is **WebServer-SG**
    +	Select **Create security group**

![securitygroupec2](/images/2.prerequisite/2.3.2.sg.png)