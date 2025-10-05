---
title : "Khởi tạo Load Balancer"
date : "2025-10-02"
weight : 4
chapter : false
pre : " <b> 4.4 </b> "
---

1. Truy cập vào **EC2**:
    -	Chọn **Load Balancers**.
    -	Chọn **Creare Load Balancer**.

![lb](/images/4.s3/4.4.1.png)

2. Phần **Load balancer types**:
    -	Chọn **HTTP/HTTPS**.
    -	Chọn **Create**.

![lb](/images/4.s3/4.4.2.png)


3. Trong giao diện **Create Application Load Balancer**:
    -	**Load balancer name**, nhập `Webserver-LB`.
    -	**Scheme**, chọn **Internet-facing**.
    -	**IP address type**, chọn **IPv4**.

![lb](/images/4.s3/4.4.3.png)

4. Thực hiện cấu hình **Network mapping**:
    -	**VPC**, chọn **wordpress-vpc**.
    -	**Mapping**, chọn **us-east-1a** và **us-east-1b**.
    -	Chọn **subnet**.

![lb](/images/4.s3/4.4.4.png)


5. Cấu hình **security group**, chọn **Webserver-SG**.
    -	Phần **Listeners and routing**, trong **Default actions** chọn **Webserver-TG**.

![lb](/images/4.s3/4.4.5.png)


6. Kiểm tra lại và chọn **Create load balancer**

![lb](/images/4.s3/4.4.66.png)


7. Tạo **Application Load Balancer** thành công và chọn **View load balancer**

    -	Chọn **Webserver-LB**.
    -	Sao chép DNS name của **Load Balancer**.

![lb](/images/4.s3/4.4.9.png)


8.	Trong giao diện **Load Balancer**. Quá trình tạo **Load Balancer** sẽ mất khoảng 5-10 phút để hoàn thành. Bạn có thể kiểm tra sự thay đổi trạng thái từ **provisioning** sang **active** ở danh sách **Load Balancer**.
    

9.	Truy cập bằng cách dán DNS name vào trình duyệt.

![lb](/images/4.s3/4.4.8.png)


Tiếp theo chúng ta sẽ tiến hành cấu hình tính năng **Auto Scaling Group**, giúp tự động tăng số lượng **EC2 instance** của chúng ta khi lượng truy cập tăng cao.