+++
title = "Select Replication Disk"
date = 2020
weight = 2
chapter = false
pre = "<b>7.2. </b>"
+++

**Contents:**
- [Trường hợp gặp phải](#trường-hợp-gặp-phải)
- [Hướng xử lý](#hướng-xử-lý)

#### Trường hợp gặp phải
- **Hệ điều hành:** Windows
- **Lỗi xảy ra:**
  - Sử dụng option --drives=<Drive letters> --force-volumes --no-prompt khi cài đặt CloudEndure Agent (VD: với <Drive letters> = c:,e:,f:,h:).
  - Cài đặt Agent thành công nhưng quá trình replication dừng tại bước **"Failed to create staging disks"**.

![CloudEndure](../../../images/7/4.png?width=50pc)

#### Hướng xử lý
Trong trường hợp sử dụng tham số truyền vào gặp phải lỗi trên, chúng ta hãy thực hiện từng bước theo yêu cầu của CloudEndure Agent để có thể lựa chọn ổ đĩa sử dụng cho quá trình replication.

Câu lệnh truyền tham số là danh sách các ổ đĩa được sử dụng cho quá trình replication:
```ps1
installer_win.exe -t EE38-668E-4BAE-3CEA-306E-2D43-F13C-1586-7F19-2221-E873-6FE0-3C48-8145-F149-907A --drives=C:,E:,F:,H: --force-volumes --no-prompt
```

Chúng ta sẽ loại bỏ các tham số truyền vào và thực hiện từng bước theo yêu cầu của Agent:
```ps1
installer_win.exe -t EE38-668E-4BAE-3CEA-306E-2D43-F13C-1586-7F19-2221-E873-6FE0-3C48-8145-F149-907A
```

![CloudEndure](../../../images/7/5.png?width=50pc)

Sau khi cài đặt xong, hãy thử vào CloudEndure console để kiểm tra kết quả thực hiện.
![CloudEndure](../../../images/7/6.png?width=90pc)
