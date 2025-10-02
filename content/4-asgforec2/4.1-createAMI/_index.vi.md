---
title : "Khởi tạo AMI từ Webserver Instance"
date : "2025-10-02"
weight : 1 
chapter : false
pre : " <b> 4.1 </b> "
---

1. Truy cập vào EC2
    -	Chọn **Instances**
    -	Chọn **webserver-ec2**
    -	Chọn **Actions**
    -	Chọn **Image and templates**
    -	Chọn **Create image**

![wp](/images/4.s3/4.1.ami.png)

2. Cấu hình Template
    -	Image name, nhập `webserver-AMI`
    -	Image description, nhập `AMI for Webserver`
    -	Chọn **Create image**

![wp](/images/4.s3/4.2.ami.png)

3. Quá trình khởi tạo AMI mất khoảng 5 phút. Sau 5 phút, chúng ta thấy Status chuyển sang **Available**

![wp](/images/4.s3/4.3.ami.png)