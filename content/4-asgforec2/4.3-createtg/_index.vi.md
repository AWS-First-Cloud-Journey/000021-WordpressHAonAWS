---
title : "Khởi tạo Target Group"
date : "2025-10-02"
weight : 3
chapter : false
pre : " <b> 4.3 </b> "
---


1. Truy cập giao diện **EC2**
    -	Chọn **Target Groups**.
    -	Chọn **Create target group**.

![ami](/images/createautoscaling/target-group-setup-01.png?featherlight=false&width=90pc)

2. Thực hiện cấu hình
    -	Chọn **Instances**.

![tg](/images/4.s3/4.3.1.png)

3. Thiết lập các thông số như sau cho target group:
    -	**Target group name:** Nhập tên của target group (VD: `Webserver-TG`).
    -	**Protocol:** HTTP.
    -	**Port:** 80.
    -	**VPC** chọn **Wordprexx-VPC**.
    -   Các mục còn lại để mặc định.
    

![tg](/images/4.s3/4.3.2.png)

4. Thiết lập **Health check**
    - **Health check protocol** chọn **HTTP**
    - **Health check path** nhập `/health`
    - -	Chọn **Next**.
    
![tg](/images/4.s3/4.3.5.png)

4. Trong giao diện Available instances
    -	Chọn **webserver instance**.
    -	Chọn **port 80**.
    -	Chọn **Include as pending below** ( nếu không chọn lúc truy cập bằng DNS Load Balancer sẽ gặp lỗi HTTP 503: Service unavailable).
    -	Kiểm tra lại.
    -	Chọn **Create target group**.

![tg](/images/4.s3/4.3.4.png)

5. Hoàn thành tạo Target group

![ami](/images/createautoscaling/target-group-setup-05.png?featherlight=false&width=90pc)
