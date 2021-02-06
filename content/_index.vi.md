+++
title = "Di chuyển ShareNote với CloudEndure"
date = 2020
weight = 1
chapter = false
+++

# Di chuyển ShareNote với CloudEndure

Bài viết này hướng dẫn cách sử dụng CloudEndure để dịch chuyển một máy ảo đang chạy ứng dụng ShareNote (có hoặc không bao gồm hệ cơ sở dữ liệu MySQL) đến một máy ảo EC2 khác.

Chúng ta sẽ sử dụng máy ảo chạy ứng dụng ShareNote ở bài thực hành [Triển khai Ứng dụng ShareNote trên Máy ảo Windows/Ubuntu]() để làm máy nguồn. Máy nguồn có thể là máy ảo chạy Linux hoặc Windows.

#### Nội dung

Nội dung chúng ta sẽ bao gồm các bài thực hành sau:

1. [AWS Credential cho CloudEndure](1-credentials/)
2. [Cấu hình CloudEndure](2-config-cloudendure/)
3. [Cài đặt Agents](3-install-agent/)
4. [Cấu hình Blueprint](4-blueprint/)
5. [Thực hiện Cutover](5-cutover/)
6. [Cấu hình Security Group](6-security-group/)