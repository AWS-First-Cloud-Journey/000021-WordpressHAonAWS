+++
title = "Cài đặt Agents"
date = 2020
weight = 3
chapter = false
pre = "<b>3. </b>"
+++

**Nội dung**
- [Thiết lập tường lửa của Máy chủ](#thiết-lập-tường-lửa-của-máy-chủ)
- [Cài đặt Agents lên máy nguồn](#cài-đặt-agents-lên-máy-nguồn)

#### Thiết lập tường lửa của Máy chủ

{{% notice note %}}
Trước khi thực hiện việc cài đặt Agent, hãy tham khảo thêm [Các yêu cầu kết nối mạng của CloudEndure](https://docs.cloudendure.com/Content/Preparing_Your_Environments/Network_Requirements/Network_Requirements.htm)
{{% /notice %}}

Để đảm bảo rằng Máy chủ nguồn có thể tương tác với CloudEndure Service Manager cũng như Máy chủ đích, bạn nên kiểm tra các thiết lập Tường lửa trên Máy chủ nguồn trước khi thực hiện migrate.

Đối với máy chủ Ubuntu, chúng ta cần mở các cổng 443 và 1500 và cho phép các luồng dữ liệu từ 2 địa chỉ IP console của CloudEndure dùng cho việc giao tiếp. Bạn có thể chạy lệnh sau:

```bash
sudo ufw allow 1500
sudo ufw allow https
sudo ufw allow from 52.72.172.158/32
sudo ufw allow from 52.53.92.136/32
```

Ngoài ra, hãy thử truy cập đến dịch vụ S3 trên AWS để chắc chắn có thể tải được ứng dụng của CloudEndure phục vụ cho quá trình migrate. Bạn có thể thử trên trình duyệt hoặc sử dụng lệnh sau trên Terminal (Linux):

```
wget s3.amazonaws.com
wget s3.us-west-1.amazonaws.com
wget s3.eu-west-1.amazonaws.com
```

#### Cài đặt Agents lên máy nguồn

**Bước 1:** Sau khi hoàn thành việc cấu hình **Replication Settings**, CloudEndure Console sẽ tự động chuyển sang trang **hướng dẫn cài đặt CloudEndure Agent** lên máy nguồn.
![Agents](../../../images/4/1.png?width=90pc)
{{% notice note %}}
Bạn cũng có thể truy cập vào trang này bằng cách chọn **Machines** từ menu bên trái.
{{% /notice %}}

**Bước 2:** Kết nối vào máy nguồn bằng **SSH (Linux)** hoặc **Remote Desktop (Windows)**.

**Bước 3:** Cài đặt **CloudEndure Agent** trên máy nguồn bằng hướng dẫn ở **Bước 1**. Thực hiện đúng hướng dẫn theo hệ điều hành của máy nguồn (Linux hoặc Windows).
CàI Agent trên máy nguồn Linux
![Agents-Linux](../../../images/4/2.png?width=90pc)
CàI Agent trên máy nguồn Windows
![Agents-Windows](../../../images/4/3.png?width=90pc)
{{% notice info %}}
Trong trường hợp bạn không thể chạy lệnh cài đặt Agent, hãy kiểm tra lại và chắc chắn bạn đã cài đặt python trong hệ điều hành.
{{% /notice %}}

**Bước 4:** Sau khi hoàn thành cài đặt CloudEndure Agent, từ **CloudEndure Console**, chọn tab **Machine**, máy nguồn sẽ được hiển thị ở đây kèm với quá trình dịch chuyển dữ liệu.

![Agents](../../../images/4/4.png?width=90pc)
