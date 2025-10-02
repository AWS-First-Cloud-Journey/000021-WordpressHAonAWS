---
title : "Khởi tạo Auto Scaling Group"
date : "2025-10-02"
weight : 5
chapter : false
pre : " <b> 4.5 </b> "
---

1. Truy cập vào EC2
-	Chọn Auto Scaling Groups
-	Chọn Create Auto Scaling group

![ami](/images/createautoscaling/auto-scaling-group-setup-01.png?featherlight=false&width=90pc)

2. Auto Scaling Group name
-	Nhập Webserver-ASG
-	Launch template. chọn Webserver-template
-	Chọn Next

![ami](/images/createautoscaling/auto-scaling-group-setup-02.png?featherlight=false&width=90pc)

3. Tiến hành cấu hình Network
•	VPC, chọn wordpress-vpc
•	Chọn AZ và subnet
•	Chọn Next


![ami](/images/createautoscaling/auto-scaling-group-setup-03.png?featherlight=false&width=90pc)

4. Thực hiện cấu hình Load balancing
-	Chọn Attach to an existing load balancer
-	Chọn Choose from your load balancer target groups
-	Chọn Webserver-TG
-	Chọn Next


![ami](/images/createautoscaling/auto-scaling-group-setup-04.png?featherlight=false&width=90pc)

5. Thực hiện cấu hình group size vè scaling policy.
-	Desired capacity: Nhập 1. (Default)
-	Minimum capacity: Nhập 1. (Default)
-	Maximum capacity: Nhập 3


![ami](/images/createautoscaling/auto-scaling-group-setup-05.png?featherlight=false&width=90pc)

6. Tại mục Scaling policies - optional: Lựa chọn trong bài thực hành này nhằm tạo điều kiện dễ dàng hơn cho bước kiểm tra được thực hiện tiếp theo. Bạn hoàn toàn có thể thiết lập chính sách scale tài nguyên theo nhu cầu của bạn.
-	Chọn Taget tracking scaling policy
-	Scaling policy name, nhập Target Tracking Policy
-	Metric type, chọn Application Load Balancer request count per target.
-	Target group, nhập FCJ-Management
-	Target value, nhập 30
-	Chọn Next

![ami](/images/createautoscaling/auto-scaling-group-setup-06.png?featherlight=false&width=90pc)

7. Chọn Next

![ami](/images/createautoscaling/auto-scaling-group-setup-07.png?featherlight=false&width=90pc)

8.	Chọn Next

![ami](/images/createautoscaling/auto-scaling-group-setup-08.png?featherlight=false&width=90pc)

9.	Chọn Create Auto Scaling group

![ami](/images/createautoscaling/auto-scaling-group-setup-09.png?featherlight=false&width=90pc)


10. Hoàn thành tạo Auto Scaling groups.

![ami](/images/createautoscaling/auto-scaling-group-setup-10.png?featherlight=false&width=90pc)


11. Quá trình khởi tạo Auto Scaling Group sẽ được thực hiện, Auto Scaling Group vừa được tạo sẽ hiển thị trong danh sách, và bạn có thể chọn vào nó để xem thông tin chi tiết.
-	Chúng ta có thể theo dõi các EC2 instance hiện có trong Auto Scaling Group ở trang Instance management. Các instance có tình trạng InService là các instance đã sẵn sàng hoạt động.

![ami](/images/createautoscaling/auto-scaling-group-setup-11.png?featherlight=false&width=90pc)
