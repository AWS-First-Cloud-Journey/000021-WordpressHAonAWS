---
title : "Phục hồi bằng DB snapshot"
date : "2025-10-02"
weight : 2
chapter : false
pre : " <b> 5.2 </b> "
---


1. Trong giao diện **RDS**

    -	Chọn **Snapshots**
    -	Chọn snapshot vừa tạo
    -	Chọn **Actions**
    -	Chọn **Restore snapshot**


![snap](/images/5.fwd/5.2.1.png)

2. Trong phần **Settings**

    -	**DB instance identifier**, nhập `wordpress-db-restore`
    -	Chọn **Multi-AZ DB  instance** vì chúng ta sử dụng multi AZ ban đầu


![snap](/images/5.fwd/5.2.2.png)

3. Thiết lập network cho **restore Database instance**

![snap](/images/5.fwd/5.2.3.png)

4. Chọn **Restore DB instance**

![snap](/images/5.fwd/5.2.4.png)

5. Đợi khoảng 10 phút, trang thái của database chuyển sang **Available** là khởi tạo thành công.

![snap](/images/5.fwd/5.2.5.png)