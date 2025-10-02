---
title : "Khởi tạo Launch Template"
date : "2025-10-02"
weight : 2
chapter : false
pre : " <b> 4.2 </b> "
---


Ở phần này, bạn sẽ tạo một Launch Template sử dụng AMI bạn đã tạo từ Amazon Linux 2 Instance ở bước trước.
1. Truy cập vào EC2
-	Chọn Launch Templates
-	Chọn Create launch template

![ami](/images/createautoscaling/launch-template-setup-01.png?featherlight=false&width=90pc)

2. Trong giao diện Create launch template
-	Launch template name, nhập Webserver-ASG-template
-	Template version description, nhập Template for Webserver ASG

![ami](/images/createautoscaling/launch-template-setup-02.png?featherlight=false&width=90pc)

3. Thực hiện chọn AMI
-	Chọn My AMIs
-	Chọn Owned by me
-	Chọn webserver-AMI

![ami](/images/createautoscaling/launch-template-setup-03.png?featherlight=false&width=90pc)

4. Thực hiện chọn Instance type
-	Chọn t2.micro
-	Key pair, chọn asg-keypair đã tạo lúc tạo EC2 instance.

![ami](/images/createautoscaling/launch-template-setup-04.png?featherlight=false&width=90pc)

5. Thực hiện cấu hình Network
-	Subnet, chọn public subnet
-	Firewall (Security Group), chọn Select existing security group
-	Chọn Webserver-SG

![ami](/images/createautoscaling/launch-template-setup-05.png?featherlight=false&width=90pc)

6. Kiểm tra lại và thực hiện Create launch template

![ami](/images/createautoscaling/launch-template-setup-06.png?featherlight=false&width=90pc)

7. Thực hiện thành công và chọn View launch templates

![ami](/images/createautoscaling/launch-template-setup-07.png?featherlight=false&width=90pc)


