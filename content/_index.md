---
title : "Triển khai Wordpress trên AWS Cloud"
date :  "`r Sys.Date()`" 
weight : 1 
chapter : false
---
# Triển khai Wordpress trên AWS Cloud

### Tổng quan

 Trong bài lab này, bạn sẽ tìm hiểu và thực hiện triển khai Wordpress trên AWS Cloud. Thực hành tạo và cài đặt Wordpress trên EC2 Instance trên public subnet kết nối đến CSDL Database trong private subnet trong VPC. Ở bài lab này đảm bảo ứng dụng Wordpress có khả năng scaling khi gặp lượng request lớn và có khả năng cân bằng tải khi có nhiều hơn một server cùng hoạt động. Database được triển khai Multi AZ cung cấp khả năng đảm bảo khả năng sẵn sàng của CSDL khi triển khai.

![ConnectPrivate](/images/diagram-wordpress-on-aws-cloud.png)

#### Amazon CloudFront
Amazon CloudFront là một dịch vụ content delivery network (CDN) được xây dựng cho việc đảm bảo hiệu năng cao, an toàn cho người sử dụng.

#### Auto Scaling Group
Auto Scaling Group (nhóm co giãn tự động) là một nhóm các EC2 Instance. Nhóm này có thể co giãn số lượng của các EC2 Instance thành viên theo chính sách co giãn (scaling policy) mà bạn đặt ra.

#### Load Balancer
Load Balancer (máy cân bằng tải) là một công cụ có thể phân phối lưu lượng dữ liệu được trao đổi tới các tài nguyên AWS (cụ thể trong bài lab này là các EC2 Instances) trong Target Group.

#### Target Group
Target Group (nhóm mục tiêu) là một nhóm những thành phần tài nguyên AWS sẽ nhận lưu lượng dữ liệu được phân phối và truyền tải bởi Load Balancer.

#### Amazon Relational Database Service (Amazon RDS)
Amazon RDS là một dịch vụ vận hành cơ sở dự liệu tự động (Database-as-a-service) cho phép bạn có thể tự động hóa quy trình tạo lập, vận hành, và mở rộng quy mô của một cơ sở dữ liệu quan hệ (relational database) trên nền tảng điện toán đám mây của AWS.

#### Multiple Availability Zone (Multi-AZ)
Multi-AZ là một tính năng cho phép bạn triển khai một bản sao dự phòng đồng bộ của cơ sở dữ liệu gốc trên một DB instance ở một Availability Zone khác. Nếu việc truy cập vào cơ sở dữ liệu gốc bị gián đoạn, bản sao dự phòng đồng bộ kia sẽ được sử dụng thay thế để đảm bảo được tính khả dụng cao cho cơ sở dữ liệu của bạn.
