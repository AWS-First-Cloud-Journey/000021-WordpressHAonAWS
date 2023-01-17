---
title : "Sao lưu và phục hồi database"
date :  "`r Sys.Date()`" 
weight : 5 
chapter : false
pre : " <b> 5. </b> "
---

Amazon RDS khởi tạo và lưu trữ tự động các bản sao lưu cho Databse (DB instance) của bạn trong khung thời gian sao lưu mà bạn thiết lập (Nếu không thiết lập, RDS sẽ tự động thiết lập là 30 phút trong khung thời gian tương ứng theo từng Region mà AWS quy định).
RDS lưu trữ tự động các bản sao lưu với khoảng thời gian tồn tại (retention period) mặc định là 7 ngày do bạn thiết lập khi khởi tạo hoặc chỉnh sửa DB Instance.

![info](/images/restoreandbackup/info-aws-01.png)

RDS sẽ tạo một bản snapshot cho storage volume của DB instance và sao lưu toàn bộ DB instance (không chỉ riêng database).
Khi cần thiết, bạn có thể khôi phục database của bạn tại bất kì thời điểm nào trong khung thời gian đó.

![info](/images/restoreandbackup/info-aws-02.png)


Để việc sao lưu tự động được thực hiện, bạn phải chắc chắn rằng:
DB instance của bạn phải đang ở trạng thái hoạt động (AVAILABLE) để quá trình sao lưu có thể thực thi. Nếu DB Instance ở trạng thái khác (ví dụ: STORAGE_FULL) thì sao lưu sẽ không được thực thi.
Việc sao lưu tự động sẽ không được thực thi nếu bạn đang copy DB instance đó trong cùng Region.


### Nội dung

 - [Khởi tạo Snapshot cho Database Instance](5.1-createdbsnapshot/)
 - [Tiến hành backup DB từ Snapshot](5.2-restorewithsnapshot//)