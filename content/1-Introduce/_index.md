---
title : "Giới thiệu"
date :  "`r Sys.Date()`" 
weight : 1 
chapter : false
pre : " <b> 1. </b> "
---

### Giới thiệu
Ở bài thực hành này, chúng ta sẽ tiến hành việc triển khai ứng dụng Wordpress với Auto Scaling Group nhằm đảm bảo khả năng co giãn của ứng dụng đó theo nhu cầu của người truy cập. Thêm vào đó, chúng ta cũng sẽ triển khai Load Balancer nhằm cân bằng tải và điều phối các yêu cầu truy cập từ phía người dùng đến Application Tier của chúng ta. Ngoài ra sử dụng thêm dịch vụ Amazon CloudFront cho ứng dụng đạt hiệu quả cao nhất.

Với phần Database Instance (DB) chúng ta sẽ triển khai CSDL trên Multi AZ và thực hiện snapshot DB để thuận tiện trong việc Roll Back cũng như đảm bảo độ sẵn sàng của dữ liệu (Multi AZ).
 
![ConnectPrivate](/images/diagram-wordpress-on-aws-cloud.png#left)


#### WordPress
WordPress là một hệ thống mã nguồn mở (Open Source Software) miễn phí để xây dựng website được viết bằng ngôn ngữ lập trình PHP cùng với cơ sở dữ liệu MySQL hoặc MariaDB.
WordPress là nền tảng tạo website dễ sử dụng và phổ biến nhất trên thế giới hiện nay cứ khoảng 10 triệu website hàng đầu có 42,8% sử dụng WordPress.
WordPress là một nền tảng xây dựng trang web tuyệt vời cho nhiều loại trang web. Ví dụ như Blog, trang bán hàng online, giới thiệu công ty, tuyển dụng,... Được xây dựng một cách tiện lợi và nhanh chóng. WordPress là một giải pháp tuyệt vời cho cá nhân và doanh nghiệp vừa và nhỏ.

#### Auto Scaling Group
Auto Scaling Group (nhóm co giãn tự động) là một nhóm các EC2 Instance. Nhóm này có thể co giãn số lượng của các EC2 Instance thành viên theo chính sách co giãn (scaling policy) mà bạn đặt ra.

#### Launch Template
Launch Template (khuôn mẫu khởi tạo) là một tính năng giúp bạn tạo khuôn mẫu cho việc khởi tạo các EC2 Instance. Nhờ thế, bạn có thể quy trình hóa và đơn giản hóa công tác khởi tạo các EC2 Instance cho dịch vụ Auto Scaling (co giãn tự động).

#### Load Balancer
Load Balancer (máy cân bằng tải) là một công cụ có thể phân phối lưu lượng dữ liệu được trao đổi tới các tài nguyên AWS (cụ thể trong bài lab này là các EC2 Instances) trong Target Group.

#### Target Group
Target Group (nhóm mục tiêu) là một nhóm những thành phần tài nguyên AWS sẽ nhận lưu lượng dữ liệu được phân phối và truyền tải bởi Load Balancer.

#### Amazon CloudFront
Amazon CloudFront là một dịch vụ content delivery network (CDN) được xây dựng cho việc đảm bảo hiệu năng cao, an toàn cho người sử dụng.

#### Amazon Relational Database Service (Amazon RDS)
Amazon RDS là một dịch vụ vận hành cơ sở dự liệu tự động (Database-as-a-service) cho phép bạn có thể tự động hóa quy trình tạo lập, vận hành, và mở rộng quy mô của một cơ sở dữ liệu quan hệ (relational database) trên nền tảng điện toán đám mây của AWS.

#### Multiple Availability Zone (Multi-AZ)
Multi-AZ là một tính năng cho phép bạn triển khai một bản sao dự phòng đồng bộ của cơ sở dữ liệu gốc trên một DB instance ở một Availability Zone khác. Nếu việc truy cập vào cơ sở dữ liệu gốc bị gián đoạn, bản sao dự phòng đồng bộ kia sẽ được sử dụng thay thế để đảm bảo được tính khả dụng cao cho cơ sở dữ liệu của bạn.
