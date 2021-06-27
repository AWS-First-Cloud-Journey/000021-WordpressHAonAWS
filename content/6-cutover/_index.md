+++
title = "Thực hiện Cutover"
date = 2020
weight = 6
chapter = false
pre = "<b>6. </b>"
+++

**Nội dung**
- [Thực hiện Cutover](#thực-hiện-cutover)

#### Thực hiện Cutover

{{% notice info %}}
Cần đợi CloudEndure **hoàn thành** việc dịch chuyển dữ liệu trước khi thực hiện Cutover, việc này có thể mấy vài phút. Khi hoàn thành việc dịch chuyển dữ liệu, trạng thái của máy nguồn sẽ chuyển thành **Continous Data Replication**.
{{% /notice %}}

	
**Bước 1:** Từ Tab **Machines** của **CloudEndure Console**, nhấn vào ô vuông bên cạnh để chọn máy nguồn.

**Bước 2:** Chọn **LAUNCH 1 TARGET MACHINE**.

**Bước 3:** Chọn **Cutover Mode**.

![Cutover](../../../images/6/1.png?width=90pc)

**Bước 4:** Ở cửa sổ pop-up hiện lên, chọn **CONTINUE**. 

![Cutover](../../../images/6/2.png?width=90pc)

{{% notice tip %}}
CloudEndure sẽ thực hiện đồng bộ dữ liệu lần cuối cùng, sau đó thực hiện việc tạo máy ảo trên môi trường AWS. 
{{% /notice %}}

**Bước 5:** Để theo dõi quá trình Cutover, chọn **Job Progress** từ menu bên trái của **CloudEndure Console**.

![Cutover](../../../images/6/3.png?width=90pc)

Đợi quá trình CutOver kết thúc.

![Cutover](../../../images/6/4.png?width=90pc)

Sau khi quá trình CutOver kết thúc, truy cập EC2 Instance để kiểm tra máy ảo đã được migrate lên.

![Cutover](../../../images/6/5.png?width=90pc)

Ngoài ra để truy cập ứng dụng ShareNote từ public bạn sẽ phải làm thêm bước 6.1
