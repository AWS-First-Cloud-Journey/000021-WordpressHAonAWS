---
title : "Khởi tạo Target Group"
date :  "`r Sys.Date()`" 
weight : 3
chapter : false
pre : " <b> 4.3 </b> "
---


1. Truy cập giao diện EC2
-	Chọn Target Groups
-	Chọn Create target group

![ami](/images/createautoscaling/target-group-setup-01.png?featherlight=false&width=90pc)

2. Thực hiện cấu hình
-	Chọn Instances

![ami](/images/createautoscaling/target-group-setup-02.png?featherlight=false&width=90pc)

3. Thiết lập các thông số như sau cho target group:
-	Target group name: Nhập tên của target group (VD: Webserver-TG).
-	Protocol: HTTP.
-	Port: 80
-	Các mục còn lại để mặc định.
-	Chon next

![ami](/images/createautoscaling/target-group-setup-03.png?featherlight=false&width=90pc)

4. Trong giao diện Available instances
-	Chọn webserver instance
-	Chọn port 80
-	Chọn Include as pending below ( nếu không chọn lúc truy cập bằng DNS Load Balancer sẽ gặp lỗi HTTP 503: Service unavailable)
-	Kiểm tra lại
-	Chọn Create target group

![ami](/images/createautoscaling/target-group-setup-04.png?featherlight=false&width=90pc)

5. Hoàn thành tạo Target group

![ami](/images/createautoscaling/target-group-setup-05.png?featherlight=false&width=90pc)
