---
title : "Khởi tạo Auto Scaling Group"
date : "2025-10-02"
weight : 5
chapter : false
pre : " <b> 4.5 </b> "
---

1. Truy cập vào **EC2**
    -	Chọn **Auto Scaling Groups**.
    -	Chọn **Create Auto Scaling group**.

![ami](/images/createautoscaling/auto-scaling-group-setup-01.png?featherlight=false&width=90pc)

2. Auto Scaling Group name
    -	Nhập `Webserver-ASG`.
    -	**Launch template**. chọn **Webserver-template**.
    -	Chọn **Next**.

![asg](/images/4.s3/4.5.1.png)

3. Tiến hành cấu hình **Network**.
    -	**VPC**, chọn **wordpress-vpc**.
    -	Chọn AZ và subnet.
    -	Chọn **Next**.


![asg](/images/4.s3/4.5.2.png)


4. Thực hiện cấu hình **Load balancing**
    -	Chọn **Attach to an existing load balancer**.
    -	Chọn **Choose from your load balancer target groups**.
    -	Chọn **Webserver-TG**.
    -	Chọn **Next**.


![asg](/images/4.s3/4.5.3.png)


5. Thực hiện cấu hình group size và scaling policy.
    -	**Desired capacity:** Nhập 1. (Default)
    -	**Minimum capacity:** Nhập 1. (Default)
    -	**Maximum capacity:** Nhập 3


![asg](/images/4.s3/4.5.4.png)


6. Tại mục **Automatic scaling - optional**: Lựa chọn trong bài thực hành này nhằm tạo điều kiện dễ dàng hơn cho bước kiểm tra được thực hiện tiếp theo. Bạn hoàn toàn có thể thiết lập chính sách scale tài nguyên theo nhu cầu của bạn.
    -	Chọn **Taget tracking scaling policy**
    -	**Scaling policy name**, nhập `Target Tracking Policy`
    -	**Metric type**, chọn **Application Load Balancer request count per target**.
    -	**Target group**, nhập `Webserver-TG`
    -	**Target value**, `nhập 30`
    -	Chọn **Next**

![asg](/images/4.s3/4.5.5.png)


7. Chọn **Next**

![asg](/images/4.s3/4.5.6.png)


8.	Chọn **Next**

![asg](/images/4.s3/4.5.7.png)

9.	Chọn **Create Auto Scaling group**

![asg](/images/4.s3/4.5.8.png)



10. Hoàn thành tạo **Auto Scaling groups.**

![asg](/images/4.s3/4.5.9.png)



💡**Tip**: Quá trình khởi tạo **Auto Scaling Group** sẽ được thực hiện, **Auto Scaling Group** vừa được tạo sẽ hiển thị trong danh sách, và bạn có thể chọn vào nó để xem thông tin chi tiết.
Chúng ta có thể theo dõi các **EC2 instance** hiện có trong **Auto Scaling Group** ở trang **Instance management**. Các instance có tình trạng **InService** là các instance đã sẵn sàng hoạt động.



