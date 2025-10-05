---
title : "Khởi tạo Cloudfront cho Web Server"
date : "2025-10-02"
weight : 6 
chapter : false
pre : "<b>6. </b>"
---


1. Truy cập **AWS Management Console**

    -	Tìm **Cloudfront**
    -	Chọn **Cloudfront**

![cf](/images/6.clean/6.1.png)

2. Trong giao diện **Cloudfront**

    -	Chọn **Create a Cloudfront Distribution**

![cf](/images/6.clean/6.2.png)


3. Trong giao diện **Create**

    - **Distribute Name** nhập `Webserver`
    - Chọn **Next**

![cf](/images/6.clean/6.3.png)

4. Trong giao diện **Specify Origin**
    - Chọn **Elastic Load Balacing**
    - Trong mục **Origin**, phần **Elastic Load Balacing origin** nhập <Load Balacing domain> tạo trước đó.
    - Path nhập `/wordpress`
    - Trong phần Setting chọn **Customize origin settings**
    - **Protocol** chọn **Only HTTP**

![cf](/images/6.clean/6.4.png)
![cf](/images/6.clean/6.4.1.png)

5. Trong giao diện **Enable Security** nhấn **Next**
    
![cf](/images/6.clean/6.5.png)
5. Trong giao diện **Review and create** nhấn **Create distribution**

![cf](/images/6.clean/6.6.png)

6. Trong giao diện **Wordpress wp-admin**

    - Chọn **Plugin**
    - Chọn **Add New**

![cf](/images/6.clean/6.7.png)

7. Trong giao diện **Plugin** của **Wordpress**

    - Gõ vào ô tìm kiếm: `WP Faster Cache`
    - Chọn `Install now`

![cf](/images/6.clean/6.8.png)


8. Sau khi cài đặt thành công quay trở lại giao diện **Plugin**
    - Chọn **Active**
    - Chọn **Plugin**
    - Tìm **WP Faster Cache** và chọn **Setting**

![cf](/images/6.clean/6.9.png)

9. Trong giao diện **WP Faster Cache**
    - Chọn **CDN** trên thanh công cụ
    - Tiếp chọn **Orther CDN Providers**

![cf](/images/6.clean/6.10.png)

10. Một hộp thoại xuất hiện tiến hành nhập
    - CDN Url: <Địa chỉ Cloudfront distribution mà bạn vừa tạo ở bước trước đó>
    - Origin Url: <DNS của Load Balancer>


![cf](/images/6.clean/6.11.png)

11. Tiếp tục chọn **Next** trong các bước tiếp theo cho tới **Finish**

![cf](/images/6.clean/6.15.png)

12. Sau khi thiết lập hoàn tất

![cf](/images/6.clean/6.16.png)

Vậy là quá trình cài đặt **CDN** cho **Wordpress** đã hoàn tất.
