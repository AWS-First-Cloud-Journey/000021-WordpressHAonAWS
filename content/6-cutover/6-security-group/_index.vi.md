+++
title = "Cấu hình Security Group"
date = 2020
weight = 1
chapter = false
pre = "<b>6.1 </b>"
+++

**Nội dung**
- [Cấu hình Security Group để truy cập ứng dụng ShareNote trên máy mục tiêu](#cấu-hình-security-group-để-truy-cập-ứng-dụng-sharenote-trên-máy-mục-tiêu)

#### Cấu hình Security Group để truy cập ứng dụng ShareNote trên máy mục tiêu
	
**Bước 1:** Từ **AWS Console**, chọn dịch vụ **EC2**. 

**Bước 2:** Ở Menu bên trái, chọn **Instances**.
	
**Bước 3:** Chọn máy ảo **trùng tên** với máy nguồn trên **CloudEndure Console**. Ghi chú lại **Public DNS** của máy ảo này trong tab **Networking**. 

![Security Group](../../../images/6/1.png?width=90pc)

**Bước 4:** Chọn Tab **Security**, phần **Security Groups**, nhấn vào **Security Group ID** được tạo tự động cho máy ảo này. 

**Bước 5:** Ở Tab **Inbound Rules**, chọn **Edit inbound rules**. 

**Bước 6:** Chọn **Add rule**, nhập các thông tin như sau:
    - Type: chọn **Custom TCP**.
    - Outgoing Port Range: Điền **8080**.
    - Source: chọn **Anywhere**.

![Security Group](../../../images/6/2.png?width=90pc)

**Bước 7:** Chọn **Save rules**.

**Bước 8:** Dùng trình duyệt để truy cập ứng dụng ShareNote theo địa chỉ ```http://<public-dns>:8080```

{{% notice info %}}
Thay ```<public-dns>``` bằng **Public DNS** của máy ảo được ghi chú lại ở **Bước 3**.
{{% /notice %}}

![Security Group](../../../images/6/3.png?width=90pc)

**Bước 9 (Không bắt buộc):** Bạn có thể thử sử dụng Elastic Load Balancer để thực hiện việc điều hướng truy cập người dùng tới Application của bạn thay vì truy cập trực tiếp vào Application Server. Bạn cũng sẽ nhận được kết quả tương tự khi truy cập vào **DNS name** của **Elastic Load Balancer**.

![Security Group](../../../images/6/4.png?width=90pc)

![Security Group](../../../images/6/3.png?width=90pc)