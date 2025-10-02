---
title : "Cài đặt wordpress trên EC2"
date : "2025-10-02" 
weight : 3 
chapter : false
pre : " <b> 3. </b> "
---
{{% notice note %}}
Chi tiết về [ kết nối EC2 Instance ](000004.awsstudygroup.com/4-launchlinuxinstance/4.2-connectlinuxinstance/)
{{% /notice %}}

1. Sau khi kết nối EC2 instance thành công. Bạn sẽ thực hiện các bước chuẩn bị để triển khai ứng dụng:

- Cài đặt dịch vụ httpd bằng cách copy câu lệnh sau:

```bash
$ sudo dnf upgrade -y
$ sudo dnf install -y httpd
```

![wp](/images/3.connect/3.1.wp.png)
![wp](/images/3.connect/3.2.wp.png)

- Cài đặt php-mysql.

```bash
$ sudo dnf install -y php-mysqli
```

![wp](/images/3.connect/3.3.wp.png)

- Cài đặt php.


```
$ sudo dnf install -y php
```

![wp](/images/3.connect/3.4.wp.png)

- Bật dịch vụ httpd và khởi động ngay lập tức.

```
$ sudo systemctl enable httpd --now
```

- Di chuyển thư mục về nơi wordpress thực thi để tiến hành tải và cài đặt.

```
$ cd /var/www/html/
$ ls
```

- Tải và cài đặt wordpress.

```
$ sudo wget https://wordpress.org/latest.tar.gz
$ sudo tar -xzf latest.tar.gz
```

![wp](/images/3.connect/3.4.3.wp.png)

- Kiểm tra kết quả tải về và giải nén.
```
$ ls
```

![wp](/images/3.connect/3.4.4.wp.png)

- Di chuyển vào thư mục wordpress và kiểm tra.
```
$ cd wordpress
$ ls
```

- Mở trình duyệt web truy cập địa chỉ ipv4 dns public của ec2 webserver (nếu không được hãy sử dụng **http**).
- Copy ipv4 dns public.

![wp](/images/3.connect/3.4.6.wp.png)

- Mở trình duyệt với Public ipv4 dns và thêm `/wordpress/wp-admin/setup-config.php`.
- Nhấn Let's go.

![wp](/images/3.connect/3.4.7.wp.png)



Thiết lập các thông số cơ bản cho wordpress
-	**Database Name:** `awsuser` (Tên của database được tạo trước đó).
-	**Username:** `admin`.
-	**Password:** `dbpassword`.
-	**Database Host**: <Your Endpoint Database>.
-	**Table Preflix:** wp_.

![wp](/images/3.connect/3.5.wp.png)

- Sau khi submit.

![wp](/images/3.connect/3.6.wp.png)

- Copy dữ liệu trong khung và nhập vào file **wp-config.php**: 

```
$ sudo nano wp-config.php
```
- **Ctrl + Shift + v** để paste dữ liệu vào file, sau đó nhấn **Ctrl + x** để thoát ra, nhấn **y** và nhấn Enter để lưu. 

![wp](/images/3.connect/3.4.8.wp.png)

Chọn run the installation để tiến hành bước tiếp theo

![install-wordpress](/images/setupwordpress/install-wordpress-setup-13.png?featherlight=false&width=90pc)

Sau khi cài đặt xong tiến hành đăng nhập vào wordpress admin

![install-wordpress](/images/setupwordpress/install-wordpress-setup-14.png?featherlight=false&width=90pc)

Đăng nhập thành công vào được giao diện dashboard của wordpress

![wp](/images/3.connect/3.9.wp.png)