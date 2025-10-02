---
title : "Khởi tạo Load Balancer"
date : "2025-10-02"
weight : 4
chapter : false
pre : " <b> 4.4 </b> "
---

1. Truy cập vào EC2
-	Chọn Load Balancers
-	Chọn Creare Load Balancer

![ami](/images/createautoscaling/loadbalancer-setup-01.png?featherlight=false&width=90pc)

2. Phần Load balancer types
-	Chọn HTTP/HTTPS
-	Chọn Create

![ami](/images/createautoscaling/loadbalancer-setup-02.png?featherlight=false&width=90pc)

3. Trong giao diện Create Application Load Balancer
-	Load balancer name, nhập Webserver-LB
-	Scheme, chọn Internet-facing
-	IP address type, chọn IPv4

![ami](/images/createautoscaling/loadbalancer-setup-03.png?featherlight=false&width=90pc)

4. Thực hiện cấu hình Network mapping
-	VPC, chọn wordpress-vpc
-	Mapping, chọn us-east-1a và us-east-1b
-	Chọn subnet

![ami](/images/createautoscaling/loadbalancer-setup-04.png?featherlight=false&width=90pc)

5. Cấu hình security group, chọn Webserver-SG.
-	Phần Listeners and routing, trong Default actions chọn Webserver-TG

![ami](/images/createautoscaling/loadbalancer-setup-05.png?featherlight=false&width=90pc)

6. Kiểm tra lại và chọn Create load balancer

![ami](/images/createautoscaling/loadbalancer-setup-06.png?featherlight=false&width=90pc)

7. Tạo Application Load Balancer thành công và chọn View load balancer

![ami](/images/createautoscaling/loadbalancer-setup-07.png?featherlight=false&width=90pc)

8.	Trong giao diện Load Balancer. Quá trình tạo Load Balancer sẽ mất khoảng 5-10 phút để hoàn thành. Bạn có thể kiểm tra sự thay đổi trạng thái từ provisioning sang active ở danh sách Load Balancer.
-	Chọn Webserver-LB
-	Sao chép DNS name của Load Balancer.

![ami](/images/createautoscaling/loadbalancer-setup-08.png?featherlight=false&width=90pc)

9.	Truy cập bằng cách dán DNS name vào trình duyệt.

![ami](/images/createautoscaling/loadbalancer-setup-09.png?featherlight=false&width=90pc)


Tiếp theo chúng ta sẽ tiến hành cấu hình tính năng Auto Scaling Group, giúp tự động tăng số lượng EC2 instance của chúng ta khi lượng truy cập tăng cao.