+++
title = "Cấu hình CloudEndure"
date = 2020
weight = 3
chapter = false
pre = "<b>3. </b>"
+++

**Nội dung**
- [Tạo dự án và cấu hình AWS Credential trên CloudEndure Console](#tạo-dự-án-và-cấu-hình-aws-credential-trên-cloudendure-console)
- [Cấu hình Replication Settings](#cấu-hình-replication-settings)

#### Tạo dự án và cấu hình AWS Credential trên CloudEndure Console

**Bước 1:** Tạo tài khoản **CloudEndure** ở [đây](https://console.cloudendure.com/#/register/register/). 

{{% notice tip %}}
Nếu bạn đã có tài khoản CloudEndure, **có thể bỏ qua** bước này.
{{% /notice %}}

**Bước 2:** Đăng nhập vào **CloudEndure Console**.
![CloudEndure](../../../images/3/1.png?width=90pc)
**Bước 3:** Từ [CloudEndure Console](https://console.cloudendure.com/), nhấn nút **Create new project** (biểu tượng dấu cộng) ở góc trên bên trái.
![CloudEndure](../../../images/3/2.png?width=90pc)
**Bước 4:** Ở ô **Project name**, đặt tên cho dự án là **MigrateVM**. Sau đó chọn **CREATE PROJECT**.

![CloudEndure](../../../images/3/3.png?width=90pc)

**Bước 5:** Ở cửa sổ pop-up **Project Not Set Up!** hiện lên, chọn **CONTINUE**.
![CloudEndure](../../../images/3/4.png?width=90pc)
{{% notice info %}}
Nếu không có cửa sổ pop-up nào hiện lên, đảm bảo rằng dự án đang chọn là **Migrate ShareNote** (góc trên bên trái). Sau đó từ menu bên trái, chọn **Setup & Info**.
{{% /notice %}}

**Bước 6:** Chọn Tab **AWS CREDENTIALS**.

**Bước 7:** Điền **AWS Access Key ID** và **AWS Secret Access Key** từ file CSV tải xuống ở [Phần 1: Tạo AWS Credential cho CloudEndure](../1-credentials/).

![CloudEndure](../../../images/3/5.png?width=90pc)

**Bước 8:** Chọn **SAVE**.

![CloudEndure](../../../images/3/6.png?width=90pc)

#### Cấu hình Replication Settings

**Bước 1:** Sau khi hoàn thành việc cấu hình **AWS Credential**, CloudEndure Console sẽ tự động chuyển sang Tab **REPLICATION SETTINGS**.

{{% notice note %}}
Bạn cũng có thể truy cập vào Tab **REPLICATION SETTINGS** bằng cách chọn **Setup & Info** từ menu bên trái, sau đó chọn Tab **REPLICATION SETTINGS**. 
{{% /notice %}}

**Bước 2:** Ở ô **Migration Source**, chọn **Other Infrastructure**.

**Bước 3:** Ở ô **Migration Target**, chọn **AWS Asia Pacific (Tokyo)**.

**Bước 4:** Ở ô **Choose the Replication Server instance type:**, chọn **t3.medium**.

**Bước 5:** Ở ô **Choose the Converter instance type**, chọn **t3.medium**.

**Bước 6:** Chọn **SAVE REPLICATION SETTINGS**.

![CloudEndure](../../../images/3/7.png?width=90pc)

**Bước 7:** Ở cửa sổ pop-up **Project setup complete**, chọn **SHOW ME HOW** để chuyển đến trang **How To Add Machines** (Hướng dẫn cài đặt CloudEndure Agent) trên máy nguồn.

![CloudEndure](../../../images/3/8.png?width=90pc)
![CloudEndure](../../../images/3/9.png?width=90pc)