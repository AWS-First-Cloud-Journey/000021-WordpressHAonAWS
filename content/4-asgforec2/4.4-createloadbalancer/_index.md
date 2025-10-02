---
title : "Create Load Balancer"
date : "2025-10-02"
weight : 4
chapter : false
pre : " <b> 4.4 </b> "
---

1. Access to EC2
- Select Load Balancers
- Select Create Load Balancer

![ami](/images/createautoscaling/loadbalancer-setup-01.png?featherlight=false&width=90pc)

2. Load balancer types section
- Select HTTP/HTTPS
- Select Create

![ami](/images/createautoscaling/loadbalancer-setup-02.png?featherlight=false&width=90pc)

3. In the Create Application Load Balancer interface
- Load balancer name, enter Webserver-LB
- Scheme, select Internet-facing
- IP address type, select IPv4

![ami](/images/createautoscaling/loadbalancer-setup-03.png?featherlight=false&width=90pc)

4. Perform Network mapping configuration
- VPC, choose wordpress-vpc
- Mapping, select us-east-1a and us-east-1b
- Select subnet

![ami](/images/createautoscaling/loadbalancer-setup-04.png?featherlight=false&width=90pc)

5. Configure the security group, select Webserver-SG.
- Section Listeners and routing, in Default actions select Webserver-TG

![ami](/images/createautoscaling/loadbalancer-setup-05.png?featherlight=false&width=90pc)

6. Check again and select Create load balancer

![ami](/images/createautoscaling/loadbalancer-setup-06.png?featherlight=false&width=90pc)

7. Create Application Load Balancer successfully and select View load balancer

![ami](/images/createautoscaling/loadbalancer-setup-07.png?featherlight=false&width=90pc)

8. In the Load Balancer interface. The Load Balancer creation process will take about 5-10 minutes to complete. You can check the status change from provisioning to active in the Load Balancer list.
- Select Webserver-LB
- Copy the DNS name of the Load Balancer.

![ami](/images/createautoscaling/loadbalancer-setup-08.png?featherlight=false&width=90pc)

9. Access by pasting the DNS name into the browser.

![ami](/images/createautoscaling/loadbalancer-setup-09.png?featherlight=false&width=90pc)


Next we will proceed to configure the Auto Scaling Group feature, which will automatically increase the number of our EC2 instances when the traffic is high.