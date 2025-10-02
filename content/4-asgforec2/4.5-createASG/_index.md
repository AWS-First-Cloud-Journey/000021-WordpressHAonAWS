---
title : "Create Auto Scaling Group"
date : "2025-10-02"
weight : 5
chapter : false
pre : " <b> 4.5 </b> "
---

1. Access to EC2
- Select Auto Scaling Groups
- Select Create Auto Scaling group

![ami](/images/createautoscaling/auto-scaling-group-setup-01.png?featherlight=false&width=90pc)

2. Auto Scaling Group name
- Enter Webserver-ASG
- Launch templates. choose Webserver-template
- Select Next

![ami](/images/createautoscaling/auto-scaling-group-setup-02.png?featherlight=false&width=90pc)

3. Proceed to configure the Network
• VPC, choose wordpress-vpc
• Select AZ and subnet
• Select Next


![ami](/images/createautoscaling/auto-scaling-group-setup-03.png?featherlight=false&width=90pc)

4. Perform Load balancing configuration
- Select Attach to an existing load balancer
- Select Choose from your load balancer target groups
- Select Webserver-TG
- Select Next


![ami](/images/createautoscaling/auto-scaling-group-setup-04.png?featherlight=false&width=90pc)

5. Configure group size and scaling policy.
- Desired capacity: Enter 1. (Default)
- Minimum capacity: Enter 1. (Default)
- Maximum capacity: Enter 3


![ami](/images/createautoscaling/auto-scaling-group-setup-05.png?featherlight=false&width=90pc)

6. Under Scaling policies - optional: Select this exercise to make it easier for the next check to be performed. You can completely set the resource scaling policy according to your needs.
- Select Target tracking scaling policy
- Scaling policy name, enter Target Tracking Policy
- Metric type, select Application Load Balancer request count per target.
- Target group, enter FCJ-Management
- Target value, enter 30
- Select Next

![ami](/images/createautoscaling/auto-scaling-group-setup-06.png?featherlight=false&width=90pc)

7. Select Next

![ami](/images/createautoscaling/auto-scaling-group-setup-07.png?featherlight=false&width=90pc)

8. Select Next

![ami](/images/createautoscaling/auto-scaling-group-setup-08.png?featherlight=false&width=90pc)

9. Select Create Auto Scaling group

![ami](/images/createautoscaling/auto-scaling-group-setup-09.png?featherlight=false&width=90pc)


10. Finish creating Auto Scaling groups.

![ami](/images/createautoscaling/auto-scaling-group-setup-10.png?featherlight=false&width=90pc)


11. The initialization of Auto Scaling Group will be done, the newly created Auto Scaling Group will be displayed in the list, and you can select it to view detailed information.
- We can track existing EC2 instances in Auto Scaling Group on the Instance management page. Instances with InService status are ready-to-go instances.

![ami](/images/createautoscaling/auto-scaling-group-setup-11.png?featherlight=false&width=90pc)