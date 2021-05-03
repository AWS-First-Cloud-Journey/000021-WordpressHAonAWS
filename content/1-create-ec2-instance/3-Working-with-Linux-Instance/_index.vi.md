+++
title = "Sử dụng Máy ảo Linux"
date = 2020-04-18T00:38:32+07:00
weight = 3
chapter = false
pre = "<b>1.1.3. </b>"
+++

> Bài thực hành sẽ thực hiện khởi tạo một Máy ảo EC2 chạy hệ điều hành Linux thông qua AWS Management Console.  

**Nội dung:**
- [Bước 1: Khởi chạy Máy ảo Linux](#bước-1-khởi-chạy-máy-ảo-linux)
- [Bước 2: Kết nối tới Máy ảo Linux](#bước-2-kết-nối-tới-máy-ảo-linux)
- [Bước 3: Xóa một Máy ảo Linux](#bước-3-xóa-một-máy-ảo-linux)

#### Bước 1: Khởi chạy Máy ảo Linux

---

> Bài thực hành sẽ thực hiện khởi tạo một Máy ảo EC2 chạy hệ điều hành Linux thông qua AWS Management Console. Ngoài ra còn có các phương thức khác để khởi tạo một máy ảo EC2 (Chi tiết bạn có thể tham khảo tại [Khởi chạy Máy ảo EC2](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/launching-instance.html)).  
> **Bắt đầu thôi!**

1. Đầu tiên, truy cập vào **Amazon EC2 console** tại https://console.aws.amazon.com/ec2/.

2. Để khởi tạo một máy ảo, chọn **Launch Instance**.

![Khởi tạo Máy ảo](/images/1/2-2-launch-instance.png?width=90pc)

3. Ở trang **Choose an Amazon Machine Image (AMI)** sẽ thể hiện một danh sách các Amazon Machine Images (AMIs). Lựa chọn AMI với tên **HVM version of Amazon Linux 2**.

![Lựa chọn Linux AMI](/images/1/2-23-select-linux-ami.png?width=90pc)

4. Tiếp đó, ở trang **Choose an Instance Type**, chúng ta sẽ lựa chọn cấu hình tài nguyên máy ảo. Lựa chọn loại ```t2.micro```.

![Lựa chọn Loại Máy ảo](/images/1/2-24-select-instance-type-linux.png?width=90pc)

5. Chọn **Review and Launch** để trình khởi tạo tự động thiết lập các thông số mặc định cho các cấu hình còn lại.
6. Ở trang **Review Instance Launch**, mục **Security Groups**, chúng ta sẽ thấy trình khởi tạo sẽ tự động tạo mới và lựa chọn một Security Group cho máy ảo. Chúng ta có thể sử dụng Security Group này hoặc lựa chọn một Security Group khác theo thiết lập của chúng ta theo các bước dưới đây:
   1. Chọn **Edit security groups**.
   2. Ở trang **Configure Security Group**, lựa chọn **Select an existing security group**.
   3. Chọn Security Group trong danh sách security group được liệt kê và chọn **Review and Launch**.
![Review Security Group](/images/1/2-25-review-security-group.png?width=90pc)
7. Ở trang **Review Instance Launch**, chọn **Launch**.

![Kiểm tra và Khởi tạo Máy ảo](/images/1/2-26-review-linux-instance-config.png?width=90pc)

8. Khi hộp thoại lựa chọn Key pair xuất hiện, chọn **Choose an existing key pair** và lựa chọn key pair trong danh sách (nếu đã được khởi tạo từ trước).  
Trường hợp chưa khởi tạo key pair, chúng ta sẽ tiến hành khởi tạo một keypair mới. Chọn **Create a new key pair**, nhập vào tên Key pair và chọn **Download Key Pair**. Đây là lần **```duy nhất```** mà chúng ta có thể tải private key của key pair; vì vậy hãy tải và lưu tập tin này cẩn thận. Chúng ta sẽ sử dụng key pair này để khởi tạo máy ảo và dùng cho mỗi lần truy cập vòa máy ảo.

![Tạo Keypair cho Máy ảo Linux](/images/1/2-27-create-linux-instance-keypair.png?width=90pc)

> **Cảnh báo**: 
> **```Không```** chọn vào **Proceed** nếu không có Keypair nào được chọn. Vì như vậy chúng ta sẽ không thể kết nối đến máy ảo khi khởi chạy máy ảo này.

Khi hoàn tất thiết lập, chọn vào hộp **Acknowledgement** và sau đó chọn **Launch Instances**.

9. Một trang xác nhận sẽ hiển thị và thông báo việc khởi tạo Máy ảo hoàn thành. Chọn **View Instances** để đóng trang và di chuyển đến Bảng điều khiển EC2.

![Hoành thành khởi tạo Máy ảo](/images/1/2-28-launch-linux-success.png?width=90pc)

10. Ở trang **Instances**, chúng ta có thể xem tiến trình khởi tạo máy ảo. Sẽ mất một khoảng thời gian ngắn để máy ảo hoàn thành việc khởi chạy. Khi khởi tạo một máy ảo, giai đoạn đầu tiên sẽ là Pending, sau đó sẽ chuyển thành Running và có Public DNS Name.
11. Sẽ mất một vài phút để máy ảo có thể hoàn thành việc khởi chạy và chúng ta có thể kết nối tới chúng. Kiểm tra tình trạng các kết quả kiểm tra ở cột **Status Checks**.

![Thông tin máy ảo Linux](/images/1/2-29-linux-instance-info.png?width=90pc)

#### Bước 2: Kết nối tới Máy ảo Linux

---

Có khá nhiều phương thức để kết nối vào một máy ảo EC2 chạy Linux. 
Trong bài thực hành này, chúng ta sẽ sử dụng **PuTTY trên Windows**  và **Windows PowerShell** để kết nối đến máy ảo Linux.

**Thực hiện kết nối vào máy ảo Linux với PuTTY trên Windows**

---

1. Trong trang **Amazon EC2 console**, lựa chọn máy ảo và chọn **Connect** trong menu **Actions**.

![Chọn Connect](/images/1/2-30-connect-linux-instance.png?width=90pc)

2. Chọn tab SSH client và lưu thông tin kết nối

![Thông tin kết nối](/images/1/2-31-get-linux-instance-public-dns.png?width=90pc)

1. Mở ứng dụng PuTTYGen để láy thông tin Private Key từ Keypair đã tải trong quá tình khởi tạo máy ảo (chuyển đổi tập tin ở dạng ```.pem``` hay ```.bib```) sang ```.ppk```.
   1. Trong **PuTTYGen**, chọn **Load** và tìm đến tập tin Keypair đã tải. (Nếu không thấy tập tin này, bạn hãy thay đổi **File type** trong cửa sổ Open sang ```All File (*.*)```)

![Chọn Keypair](/images/1/2-32-load-linux-keypair.png?width=50pc)

   2. Chọn **Save private key** để lưu lại Private key ở dạng ```.ppk```.

![Lưu Private Key](/images/1/2-33-save-linux-private-key.png?width=50pc)

4. Mở ứng dụng PuTTY để kết nối vào Máy ảo Linux:
   1. **Host Name** sẽ điền ở dạng ```<username>@<Public DNS>``` (Danh sách username có thể tìm thấy ở [Thông số Chung cho việc kết nối đến Máy ảo EC2](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/connection-prereqs.html))
   2. Trong PuTTY, đi đến **Connection > SSH > Auth** và chọn Private key đã lưu ở bước trước.
   3. Cuối cùng, chọn **Open** để kết nối đến máy ảo.
![Cấu hình Authentication](/images/1/2-34-athentication-configure.png?width=50pc)

![Kết nối đến máy ảo Linux](/images/1/2-35-connecting-to-linux-instance.png?width=50pc)

5. Nếu xuất hiện hộp thoại **PuTTY Security Alert**, chọn **Yes** để chấp nhận host key để lưu thông tin vào cache và tiếp tục quá trình kết nối. Cửa sổ dòng lệnh sẽ xuất hiện sau khi kết nối SSH được thiết lập thành công.

![Hoàn thành kết nối SSH](/images/1/2-36-successfully-ssh-linux-instance.png?width=50pc)

---

**Thực hiện kết nối vào máy ảo Linux bằng Windows PowerShell**

---
1. Trong trang **Amazon EC2 console**, lựa chọn máy ảo và chọn **Connect** trong menu **Actions**.

![Chọn Connect](/images/1/2-30-connect-linux-instance.png?width=90pc)

2. Chọn tab SSH client và lưu thông tin kết nối

![Thông tin kết nối](/images/1/2-31-get-linux-instance-public-dns.png?width=90pc)
3. Mở Windows PowerShell và chạy lệnh kết nối đã lưu ở bước trên.
![Kết nối](/images/1/2-37-connect-with-powershell.png?width=90pc)

#### Bước 3: Xóa một Máy ảo Linux

---

Việc này sẽ tương tự với việc ngưng hoạt động một máy ảo Windows. Bạn có thể quay lại [Xóa một Máy ảo Windows](../2-working-with-windows-instance/#bước-3-xóa-một-máy-ảo-windows)

**Để ngưng hoạt động (xóa) máy ảo**

---

1. Ở bảng điều hướng, chọn **Instances**. Chọn máy ảo cần xóa trong danh sách máy ảo.
2. Chọn **Actions > Instance State > Terminate**.
3. Chọn **Yes, Terminate** khi hộp thoại yêu cầu xác nhận xuất hiện.

Amazon EC2 sẽ tắt và xóa máy ảo. Sau khi máy ảo được xóa, thông tin về máy ảo vẫn được hiển thị ở danh sách một khoảng thời gian, sau đó sẽ được xóa bỏ hoàn toàn.
![Delete](/images/1/2-38-delete-ec2.png?width=90pc)