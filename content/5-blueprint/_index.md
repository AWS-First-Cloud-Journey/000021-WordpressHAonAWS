+++
title = "Cấu hình Blueprint"
date = 2020
weight = 4
chapter = false
pre = "<b>4. </b>"
+++

**Nội dung**
- [Cấu hình Blueprint cho máy mục tiêu](#cấu-hình-blueprint-cho-máy-mục-tiêu)

#### Cấu hình Blueprint cho máy mục tiêu 
Blueprint là đặc tả cho máy mục tiêu trên môi trường AWS, bao gồm loại máy (VD: t3.medium), subnet, private ip, loại ổ đĩa EBS. 

{{% notice note %}}
Có thể thực hiện Blueprint **trong lúc** đợi CloudEndure dịch chuyển dữ liệu từ máy nguồn.
{{% /notice %}}
	
**Bước 1:** Từ Tab **Machines** của **CloudEndure Console**, bấm vào tên của máy nguồn để truy cập thông tin máy.

{{% notice info %}}
Không chọn vào ô vuông bên cạnh máy nguồn.
{{% /notice %}}

**Bước 2:** Ở Tab **BLUEPRINT**, ô **Machine Type**, chọn **t3.medium**.

**Bước 3:** Chọn **SAVE BLUEPRINT**.

![Blueprint](../../../images/5/1.png?width=90pc)

**Bước 4:** Nếu có cửa sổ pop-up **Security Warning** hiện lên, chọn **OK**.
![Blueprint](../../../images/5/2.png?width=90pc)