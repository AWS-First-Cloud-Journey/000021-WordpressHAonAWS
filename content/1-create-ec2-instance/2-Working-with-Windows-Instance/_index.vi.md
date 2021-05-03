+++
title = "Sử dụng Máy ảo Windows"
date = 2020-04-18T00:38:32+07:00
weight = 2
chapter = false
pre = "<b>1.2. </b>"
+++

> Bài thực hành sẽ thực hiện khởi tạo một Máy ảo EC2 chạy hệ điều hành Windows thông qua AWS Management Console.

**Nội dung:**
- [Bước 1: Khởi chạy Máy ảo Windows](#bước-1-khởi-chạy-máy-ảo-windows)
- [Bước 2: Kết nối tới Máy ảo Windows](#bước-2-kết-nối-tới-máy-ảo-windows)
- [Bước 3: Xóa một Máy ảo Windows](#bước-3-xóa-một-máy-ảo-windows)

#### Bước 1: Khởi chạy Máy ảo Windows

---

> Bài thực hành sẽ thực hiện khởi tạo một Máy ảo EC2 chạy hệ điều hành Windows thông qua AWS Management Console. Ngoài ra còn có các phương thức khác để khởi tạo một máy ảo EC2 (Chi tiết bạn có thể tham khảo tại [Khởi chạy Máy ảo EC2](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/launching-instance.html)).  
> **Bắt đầu thôi!**

1. Đầu tiên, truy cập vào **Amazon EC2 console** tại https://console.aws.amazon.com/ec2/.


2. Để khởi tạo một máy ảo, chọn **Launch Instance**.

![Khởi tạo Máy ảo](/images/1/2-2-launch-instance.png?width=90pc)

3. Ở trang **Choose an Amazon Machine Image (AMI)** sẽ thể hiện một danh sách các Amazon Machine Images (AMIs). Lựa chọn AMI với tên **Windows Server 2019 Base** hoặc mới hơn.

![Lựa chọn Windows AMI](/images/1/2-3-select-windows-ami.png?width=90pc)

4. Tiếp đó, ở trang **Choose an Instance Type**, chúng ta sẽ lựa chọn cấu hình tài nguyên máy ảo. Lựa chọn loại ```t2.micro```.

![Lựa chọn Loại Máy ảo](/images/1/2-4-select-instance-type-windows.png?width=90pc)

5. Chọn **Review and Launch** để trình khởi tạo tự động thiết lập các thông số mặc định cho các cấu hình còn lại.
6. Ở trang **Review Instance Launch**, mục **Security Groups**, chúng ta sẽ thấy trình khởi tạo sẽ tự động tạo mới và lựa chọn một Security Group cho máy ảo. Chúng ta có thể sử dụng Security Group này hoặc lựa chọn một Security Group khác theo thiết lập của chúng ta theo các bước dưới đây:
   1. Chọn **Edit security groups**.
   2. Ở trang **Configure Security Group**, lựa chọn **Select an existing security group**.
   3. Chọn Security Group trong danh sách security group được liệt kê và chọn **Review and Launch**.

![Điều chỉnh Security Group](/images/1/2-5-config-ec2-sg.png?width=90pc)

7. Ở trang **Review Instance Launch**, chọn **Launch**.

![Kiểm tra và Khởi tạo Máy ảo](/images/1/2-6-review-windows-instance-config.png?width=90pc)

8. Khi hộp thoại lựa chọn Key pair xuất hiện, chọn **Choose an existing key pair** và lựa chọn key pair trong danh sách (nếu đã được khởi tạo từ trước).

![Chọn Keypair cho Máy ảo](/images/1/2-7-select-keypair-windows-instance.png?width=90pc)

Trường hợp chưa khởi tạo key pair, chúng ta sẽ tiến hành khởi tạo một keypair mới. Chọn **Create a new key pair**, nhập vào tên Key pair và chọn **Download Key Pair**. Đây là lần **```duy nhất```** mà chúng ta có thể tải private key của key pair; vì vậy hãy tải và lưu tập tin này cẩn thận. Chúng ta sẽ sử dụng key pair này để khởi tạo máy ảo và dùng cho mỗi lần truy cập vào máy ảo.

![Tạo Keypair cho Máy ảo Windows](/images/1/2-8-create-windows-instance-keypair.png?width=90pc)

> **Cảnh báo**: 
> **```Không```** chọn vào **Proceed** nếu không có Keypair nào được chọn. Vì như vậy chúng ta sẽ không thể kết nối đến máy ảo khi khởi chạy máy ảo này.

Khi hoàn tất thiết lập, chọn vào hộp **Acknowledgement** và sau đó chọn **Launch Instances**.

9. Một trang xác nhận sẽ hiển thị và thông báo việc khởi tạo Máy ảo hoàn thành. Chọn **View Instances** để đóng trang và di chuyển đến Bảng điều khiển EC2.

![Hoành thành khởi tạo Máy ảo](/images/1/2-9-launch-windows-success.png?width=90pc)

10. Ở trang **Instances**, chúng ta có thể xem tiến trình khởi tạo máy ảo. Sẽ mất một khoảng thời gian ngắn để máy ảo hoàn thành việc khởi chạy. Khi khởi tạo một máy ảo, giai đoạn đầu tiên sẽ là Pending, sau đó sẽ chuyển thành Running và có Public DNS Name.
11. Sẽ mất một vài phút để máy ảo có thể hoàn thành việc khởi chạy và chúng ta có thể kết nối tới chúng. Kiểm tra tình trạng các kết quả kiểm tra ở cột **Status Checks**.

![Thông tin máy ảo Windows](/images/1/2-10-windows-instance-info.png?width=90pc)

#### Bước 2: Kết nối tới Máy ảo Windows

---

Để kết nối tới một máy ảo Windows, chúng ta sẽ phải lấy thông tin mật khẩu tài khoản administrator (ở bước 2) và sử dụng mật khẩu này để đăng nhập vào Windows khi kết nối thông qua Remote Desktop.
> **Ghi chú**:  
> - Tên của tài khoản administrator sẽ phụ thuộc vào ngôn ngữ của hệ điều hành. Ví dụ như đối với tiếng Anh sẽ là Administrator, đối với tiếng Pháp sẽ là Administrateur và tiếng Bồ Đào Nha sẽ là Administrador.  
> - Bản quyền của hệ điều hành Windows Server (OS) sẽ cho phép 2 kết nối đồng thời phục vụ cho việc quản trị hệ thống. Chi phí về bản quyền đã được tính vào chi phí của một máy ảo. Nếu chúng ta cần nhiều hơn hai kết nối, chúng ta phải chi trả thêm bản quyền cho Dịch vụ Remote Desktop. Nếu không, khi có kết nối thứ ba, sẽ có thông báo lỗi được trả về.

**Thực hiện kết nối vào máy ảo Windows với ứng dụng RDP**

---

1. Trong trang **Amazon EC2 console**, lựa chọn máy ảo và chọn **Connect** trong menu **Actions**.

![Chọn Connect](/images/1/2-11-connect-windows-instance.png?width=90pc)

2. Ở hộp thoại **Connect To Your Instance**, chọn **Get Password** (sẽ mất một khoảng thời gian ngắn sau khi khởi tạo để có thể lấy được mật khẩu).

![Lấy thông tin Mật khẩu](/images/1/2-12-get-windows-instance-admin-password.png?width=90pc)

3. Chọn **Browse** và chọn đến tập tin Keypair đã được tải về khi khởi tạo máy ảo. Lựa chọn tập tin và chọn **Open** để thông tin keypair được nhập vào khung **Contents**.

![Lựa chọn Keypair để Giải mã](/images/1/2-13-select-keypair-to-decrypt-admin-password.png?width=90pc)

4. Chọn **Decrypt Password**. Khung điều khiển sẽ hiện mật khẩu mặc định của máy ảo ở hộp thoại **Connect To Your Instance**, thay cho nút **Get Password**.

![Giải mã Mật khẩu thành công](/images/1/2-14-successfully-get-password.png?width=90pc)

1. Lưu lại mật khẩu mặc định và sao chép chúng vào clipboard. Chúng ta sẽ sử dụng mật khẩu này để truy cập vào máy ảo. 
2. Chọn **Download Remote Desktop File**. Trình duyệt sẽ cho phép chúng ta lựa chọn Mở hoặc Lưu tập tin ```.rdp```. Lựa chọn Save để lưu tập tin về máy.
3. Mở tập tin ```.rdp``` đã tải về, chúng ta sẽ thấy xuất hiện hộp thoại **Remote Desktop Connection**.
4. Chúng ta có thể sẽ thấy xuất hiện một bảng cảnh báo về Publisher chưa được xác định khi kết nối. Chọn **Connect** để tiếp tục kết nối đến máy ảo.

![Chấp nhận Publisher](/images/1/2-15-connecting-to-windows-instance.png?width=30pc)

9. Khi khung yêu cầu đăng nhập, chúng ta sẽ sử dụng tài khoản Administrator được đề cập ở trên cùng với Mật khẩu đã được lưu (hoặc sao chép vào clipboard) để đăng nhập vào máy ảo. Nếu khung đăng nhập đã lưu một tài khoản đăng nhập khác, chúng ta có thể chọn **Use another account** và nhập thông tin tài khoản và mật khẩu của chúng ta vào.

> **Ghi chú**:
> Trong một số trường hợp, việc sao chép và dán nội dung có thể phát sinh lỗi dữ liệu. Nếu việc đăng nhập xảy ra lỗi "Password Failed", hãy thử nhập tay mật khẩu để thử lại.

![Đăng nhập vào Máy ảo](/images/1/2-16-login-windows-instance.png?width=30pc)

10. Do sử dụng self-signed certificates, chúng ta có thể sẽ thấy xuất hiện khung cảnh báo bảo mật về việc xác thực certificate. Chọn **Yes** hoặc **Continue** để tiếp tục.

![Chấp nhận Certificate](/images/1/2-17-accept-cerificate-windows-instance.png?width=30pc)

11. Khung cửa sổ RDP sẽ hiển thị Desktop của máy ảo Windows khi kết nối thành công.

![Kết nối thành công đến Máy ảo Windows](/images/1/2-18-successfully-rdp-windows-instance.png?width=50pc)

{{% notice warning %}}
Nếu gặp lỗi trong quá trình kết nối tới EC2, hãy kiểm tra lại Inbound rule của Security Group được gán cho EC2.\
Truy cập EC2 Console => Security Group.\
Chọn security group được dùng ở bước trước.\
Chọn **Action | Edit Inbound rules**
![Chọn Edit Inbound rule Security Group](/images/1/2-19-choose-edit-inbound-rule.png?width=90pc)
Sửa **Source** thành **Anywhere** và chọn **Save rules**
![Thay đổi Source thành Anywhere](/images/1/2-20-change-source-to-anywhere.png?width=90pc)

{{% /notice %}}
#### Bước 3: Xóa một Máy ảo Windows

---

Sau khi hoàn thành các bước khởi tạo và kết nối đến máy ảo, hãy thử tìm hiểu và thao tác thêm trên máy ảo này. Sau đó chúng ta nên dọn dẹp bằng việc ngưng hoạt động của máy ảo.

> **Quan trọng**:
> Ngưng hoạt động máy ảo đồng nghĩa với việc xóa máy ảo. Chúng ta sẽ không thể kết nối với máy ảo này nếu chúng đã bị xóa.

Nếu bạn khởi chạy một máy ảo không nằm trong AWS Free Tier, bạn sẽ không bị thu phí khi máy ảo ở trạng thái ```shutting down``` hay ```terminated```. Nếu muốn lưu giữ máy ảo ở trạng thái không bị thu phí và có thể sử dụng lại khi cần thiết, chúng ta có thể **Stop** máy ảo thay vì **Terminate**.

**Để ngưng hoạt động (xóa) máy ảo**

---

1. Ở bảng điều hướng, chọn **Instances**. Chọn máy ảo cần xóa trong danh sách máy ảo.
2. Chọn **Actions > Instance State > Terminate**.

![Xóa một Máy ảo](/images/1/2-21-terminate-windows-instance.png?width=90pc)

3. Chọn **Yes, Terminate** khi hộp thoại yêu cầu xác nhận xuất hiện.

![Xác nhận Xóa máy ảo](/images/1/2-22-terminate-windows-instance-confirm.png?width=90pc)

Amazon EC2 sẽ tắt và xóa máy ảo. Sau khi máy ảo được xóa, thông tin về máy ảo vẫn được hiển thị ở danh sách một khoảng thời gian, sau đó sẽ được xóa bỏ hoàn toàn.
