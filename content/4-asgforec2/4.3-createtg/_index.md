=---
title : "Create Target Group"
date : "`r Sys.Date()`"
weight : 3
chapter : false
pre : " <b> 4.3 </b> "
---


1. Access the EC2 interface
- Select Target Groups
- Select Create target group

![ami](/images/createautoscaling/target-group-setup-01.png?featherlight=false&width=90pc)

2. Make configuration
- Select Instances

![ami](/images/createautoscaling/target-group-setup-02.png?featherlight=false&width=90pc)

3. Set the following parameters for the target group:
- Target group name: Enter the name of the target group (eg Webserver-TG).
- Protocol: HTTP.
- Port: 80
- The remaining items leave the default.
- Select next

![ami](/images/createautoscaling/target-group-setup-03.png?featherlight=false&width=90pc)

4. In the Available instances . interface
- Select webserver instance
- Select port 80
- Select Include as pending below (if not selected when accessing with DNS Load Balancer will get an HTTP 503: Service unavailable error)
-	Review
- Select Create target group

![ami](/images/createautoscaling/target-group-setup-04.png?featherlight=false&width=90pc)

5. Finish creating Target group

![ami](/images/createautoscaling/target-group-setup-05.png?featherlight=false&width=90pc)