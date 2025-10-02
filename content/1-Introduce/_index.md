---
title : "Introduction"
weight : 1
date : "2025-10-02"
chapter : false
pre : " <b> 1. </b> "
---

### Introduce
In this exercise, we will conduct the deployment of a Wordpress application with Auto Scaling Group to ensure the scalability of the application according to the needs of the visitors. In addition, we will also implement a Load Balancer to balance the load and coordinate user access requests to our Application Tier. In addition, use the Amazon CloudFront service for the most effective application.

With the Database Instance (DB) part, we will deploy the database on Multi AZ and take a DB snapshot to facilitate Roll Back as well as ensure data availability (Multi AZ).
 
![ConnectPrivate](/images/diagram-wordpress-on-aws-cloud.png#left)

#### WordPress
WordPress is a free and open source system for building websites written in the PHP programming language along with a MySQL or MariaDB database.
WordPress is the easiest to use and most popular website building platform in the world today, 42.8% of the top 10 million websites use WordPress.
WordPress is a great website building platform for many types of websites. For example, Blog, online sales page, company introduction, recruitment,... Built in a convenient and fast way. WordPress is a great solution for individuals and small and medium businesses.

#### Auto Scaling Group
Auto Scaling Group is a group of EC2 Instances. This group can scale the number of EC2 Instance members according to the scaling policy you set.

#### Launch Template
Launch Template is a feature that helps you create a template for the initialization of EC2 Instances. As a result, you can streamline and simplify the creation of EC2 Instances for the Auto Scaling service.

#### Load Balancer
The Load Balancer is a tool that can distribute the traffic of exchanged data to AWS resources (specifically in this lab, EC2 Instances) in the Target Group.

#### Target Group
The Target Group is a group of AWS resource elements that will receive data traffic delivered and transported by the Load Balancer.

#### Amazon CloudFront
Amazon CloudFront is a content delivery network (CDN) service built for high-performance, secure user experience.

#### Amazon Relational Database Service (Amazon RDS)
Amazon RDS is an automated database operation service (Database-as-a-service) that allows you to automate the creation, operation, and scaling of a database. relational database on the AWS cloud computing platform.

#### Multiple Availability Zone (Multi-AZ)
Multi-AZ is a feature that allows you to deploy a synchronous backup copy of the original database on a DB instance in a different Availability Zone. If access to the original database is interrupted, the other synchronous backup will be used instead to ensure high availability for your database.