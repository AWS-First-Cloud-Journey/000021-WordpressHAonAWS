---
title : "Khởi tạo Cloudfront cho Web Server"
date : "2025-10-02"
weight : 6 
chapter : false
pre : "<b>6. </b>"
---


1. Truy cập AWS Management Console
-	Tìm Cloudfront
-	Chọn Cloudfront

![cloudfront](/images/setupcloudfront/setup-cloud-front-01.png?featherlight=false&width=90pc)

2. Trong giao diện Cloudfront
-	Chọn Create a Cloudfront Distribution

![cloudfront](/images/setupcloudfront/setup-cloud-front-02.png?featherlight=false&width=90pc)


3. Trong giao diện Create
- Origin domain chọn Load Balancer domain

![cloudfront](/images/setupcloudfront/setup-cloud-front-03.png?featherlight=false&width=90pc)

4. Tiếp theo để mọi thứ mặc định và chọn Create distribution

![cloudfront](/images/setupcloudfront/setup-cloud-front-04.png?featherlight=false&width=90pc)

5. Sau khi tạo thành công Cloudfront Distribution quá trình khởi tạo khoảng 5 phút.
- Lưu lại giá trị Distribution Domain Name để tiến hành cài đặt ở bước tiếp theo


![cloudfront](/images/setupcloudfront/setup-cloud-front-05.png?featherlight=false&width=90pc)

6. Trong giao diện Wordpress wp-admin
- Chọn Plugin
- Chọn Add New

![cloudfront](/images/setupcloudfront/setup-cloud-front-06.png?featherlight=false&width=90pc)

7. Trong giao diện Plugin của Wordpress
- Gõ vào ô tìm kiếm: WP Faster Cache
- Chọn Install now

![cloudfront](/images/setupcloudfront/setup-cloud-front-07.png?featherlight=false&width=90pc)


8. Sau khi cài đặt thành công quay trở lại giao diện Plugin
- Chọn Plugin
- Tìm WP Faster Cache và chọn setting

![cloudfront](/images/setupcloudfront/setup-cloud-front-08.png?featherlight=false&width=90pc)

9. Trong giao diện WP Faster Cache
- Chọn CDN trên thanh công cụ
- Tiếp chọn Orther CDN Providers

![cloudfront](/images/setupcloudfront/setup-cloud-front-09.png?featherlight=false&width=90pc)

10. Một hộp thoại xuất hiện tiến hành nhập
- CDN Url: <địa chỉ Cloudfront distribution mà bạn vừa tạo ở bước trước đó>
- Origin Url: <địa chỉ dns ipv4 của ec2 instance webserver>


![cloudfront](/images/setupcloudfront/setup-cloud-front-10.png?featherlight=false&width=90pc)

11. Tiếp tục chọn Next trong các bước tiếp theo cho tới finish

![cloudfront](/images/setupcloudfront/setup-cloud-front-11.png?featherlight=false&width=90pc)

12. Sau khi thiết lập hoàn tất

![cloudfront](/images/setupcloudfront/setup-cloud-front-12.png?featherlight=false&width=90pc)

Vậy là quá trình cài đặt CDN cho Wordpress đã hoàn tất.
