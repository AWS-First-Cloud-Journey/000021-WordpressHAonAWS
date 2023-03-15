---
title : "Launch Database Instance"
date : "`r Sys.Date()`"
weight : 5
chapter : false
pre : " <b> 2.5 </b> "
---

{{% notice note %}}
We perform **Database Instance** initialization in **Private subnet** for the purpose of protecting **DB Instance** connection only for **EC2 Web server** access.
{{% /notice %}}

1. Access **AWS Management Console**
- Find **RDS**
- Select **RDS**

![db](/images/createdatabase/db-setup-0.png?featherlight=false&width=90pc)

2. In the **Amazon RDS** interface
- Select **Create Database**

![db](/images/createdatabase/db-setup-1.png?featherlight=false&width=90pc)

3. Proceed to configure
- Select **Standard create**
- In Engine options, select **MySQL**
- Select the **SQL** version suitable for **Wordpress** (version 5.7)


![db](/images/createdatabase/db-setup-2.png?featherlight=false&width=90pc)

4. In the Template section
- Select **Production** to use **Availability** and **durability** (can choose **Multi-AZ DB instance** or **Multi-AZ DB Cluster** or **Single DB instance**). In the lab using **Multi-AZ DB instance** does not support **Multi-AZ DB cluster snapshot**
- In Engine options, select MySQL.

![db](/images/createdatabase/db-setup-3.png?featherlight=false&width=90pc)

{{% notice note %}}
If you choose the Free tier, you won't use Availability and durability, you can't choose the Deployment type
{{% /notice %}}

{{% notice tip %}}
For deployment in Dev/Test (or Production) environment, you should choose Multi-AZ deployment to create an additional standby instance in another AZ for redundancy.
{{% /notice %}}



5. Configure information about **Database**
- **DB instance identifier**, enter **wordpress-db**
- **Master username**, enter **admin**
- **Master password**, enter your password. Example lab: dbpassword
- **Confirm password**, re-enter the password.

![db](/images/createdatabase/db-setup-4.png?featherlight=false&width=90pc)

6. Configure Instance and Storage to Default

![db](/images/createdatabase/db-setup-5.png?featherlight=false&width=90pc)

7. Network configuration for DB instance
- **Network type**, select **IPv4**
- **VPC**, select the VPC for the created lab
- **Subnet group**, select **Create new DB subnet Group**
- **Public access**, select **No**
- For **VPC Security group**, select **Choose existing**
- Select **DB instance SG**

![db](/images/createdatabase/db-setup-6.png?featherlight=false&width=90pc)

8. Database Configuration
- **Initial database name**, enter **awsuser**
- Remaining items to default

![db](/images/createdatabase/db-setup-7.png?featherlight=false&width=90pc)

9. Wait about 10 minutes, finish creating DB instance and Status of DB instance changes to Available

![db](/images/createdatabase/db-setup-8.png?featherlight=false&width=90pc)

10. In the interface **DB instance** just created
- Select **Connectivity & security**
- Store **Enpoint & port** of **DB instance** to perform next steps configuration.

![db](/images/createdatabase/db-setup-9.png?featherlight=false&width=90pc)