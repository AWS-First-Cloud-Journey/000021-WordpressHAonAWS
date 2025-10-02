---
title : "Phục hồi bằng DB snapshot"
date : "2025-10-02"
weight : 2
chapter : false
pre : " <b> 5.2 </b> "
---


1. Trong giao diện RDS
-	Chọn Snapshots
-	Chọn snapshot vừa tạo
-	Chọn Actions
-	Chọn Restore snapshot


![info](/images/restoreandbackup/restore-snapshot-setup-01.png?featherlight=false&width=90pc)

2. Trong phần Settings
-	DB instance identifier, nhập wordpress-db-restore
-	Chọn create a standby instance vì chúng ta sử dụng multi AZ ban đầu


![info](/images/restoreandbackup/restore-snapshot-setup-02.png?featherlight=false&width=90pc)

3. Thiết lập network cho restore Database instance

![info](/images/restoreandbackup/restore-snapshot-setup-03.png?featherlight=false&width=90pc)

4. Chọn Restore DB instance

![info](/images/restoreandbackup/restore-snapshot-setup-04.png?featherlight=false&width=90pc)

5. Đợi khoảng 10 phút, trang thái của database chuyển sang Available là khởi tạo thành công.

![info](/images/restoreandbackup/restore-snapshot-setup-05.png?featherlight=false&width=90pc)
