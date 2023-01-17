---
title : "Cài đặt wordpress trên EC2"
date :  "`r Sys.Date()`" 
weight : 3 
chapter : false
pre : " <b> 3. </b> "
---
{{% notice note %}}
Chi tiết về [ kết nối EC2 Instance ](000004.awsstudygroup.com/4-launchlinuxinstance/4.2-connectlinuxinstance/)
{{% /notice %}}

1. Sau khi kết nối EC2 instance thành công. Bạn sẽ thực hiện các bước chuẩn bị để triển khai ứng dụng:

- Cài đặt dịch vụ httpd bằng cách copy câu lệnh sau:

```
sudo yum install -y httpd
```

![install-wordpress](/images/setupwordpress/install-wordpress-setup-0.png?featherlight=false&width=90pc)

- Cài đặt php-mysql

```
sudo yum install php-mysql -y
```

![install-wordpress](/images/setupwordpress/install-wordpress-setup-1.png?featherlight=false&width=90pc)

- Cài đặt php7.3

```
sudo amazon-linux-extras install -y php7.3
```
![install-wordpress](/images/setupwordpress/install-wordpress-setup-2.png?featherlight=false&width=90pc)

Di chuyển thư mục về nơi wordpress thực thi để tiến hành tải và cài đặt
```
$ cd /var/www/html/
$ ls
```
![install-wordpress](/images/setupwordpress/install-wordpress-setup-3.png?featherlight=false&width=90pc)

- Tải và cài đặt wordpress
```
$ wget https://wordpress.org/latest.tar.gz
$ tar -xzf latest.tar.gz
```

![install-wordpress](/images/setupwordpress/install-wordpress-setup-4.png?featherlight=false&width=90pc)

- Kiểm tra kết quả tải về và giải nén
```
$ ls
```

![install-wordpress](/images/setupwordpress/install-wordpress-setup-5.png?featherlight=false&width=90pc)

- Di chuyển vào thư mục wordpress và kiểm tra
```
$ cd wordpress
$ ls
```
![install-wordpress](/images/setupwordpress/install-wordpress-setup-6.png?featherlight=false&width=90pc)

Mở trình duyệt web truy cập địa chỉ ipv4 dns public của ec2 webserver
- Copy ipv4 dns public

![install-wordpress](/images/setupwordpress/install-wordpress-setup-7.png?featherlight=false&width=90pc)

-	Mở trình duyệt với Public ipv4 dns và thêm /wordpress/wp-admin/setup-config.php

![install-wordpress](/images/setupwordpress/install-wordpress-setup-8.png?featherlight=false&width=90pc)

Thiết lập các thông số cơ bản cho wordpress
-	Database Name: awsuser (Tên của database được tạo trước đó)
-	Username: admin
-	Password: dbpassword
-	Database Host: Your Endpoint Database
-	Table Preflix: wp_

![install-wordpress](/images/setupwordpress/install-wordpress-setup-9.png?featherlight=false&width=90pc)

Sau khi submit 

![install-wordpress](/images/setupwordpress/install-wordpress-setup-10.png?featherlight=false&width=90pc)

Đổi tên file wp-config-sample.php thành file wp-config.php
```
$ mv wp-config-sample.php wp-config.php
```

![install-wordpress](/images/setupwordpress/install-wordpress-setup-11.png?featherlight=false&width=90pc)

Xóa dữ liệu trong file wp-config.php và tiến hành sao chép thông tin ở bước trước đó vào file wp-config.php
```
	$ cat > wp-config.php
	$ nano wp-config.php
```

![install-wordpress](/images/setupwordpress/install-wordpress-setup-12.png?featherlight=false&width=90pc)

Chọn run the installation để tiến hành bước tiếp theo

![install-wordpress](/images/setupwordpress/install-wordpress-setup-13.png?featherlight=false&width=90pc)

Sau khi cài đặt xong tiến hành đăng nhập vào wordpress admin

![install-wordpress](/images/setupwordpress/install-wordpress-setup-14.png?featherlight=false&width=90pc)

Đăng nhập thành công vào được giao diện dashboard của wordpress

![install-wordpress](/images/setupwordpress/install-wordpress-setup-15.png?featherlight=false&width=90pc)