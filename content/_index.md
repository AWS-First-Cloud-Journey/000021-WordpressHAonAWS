---
title : "Deploying Wordpress on AWS Cloud"
date : "`r Sys.Date()`"
weight : 1
chapter : false
---
# Deploy Wordpress on AWS Cloud

### Overview

 In this lab, you will learn and implement Wordpress deployment on AWS Cloud. Practice creating and installing Wordpress on EC2 Instance on public subnet connecting to Database Database in private subnet in VPC. This lab ensures that the Wordpress application has the ability to scale when encountering a large number of requests and has the ability to balance the load when more than one server is running. Database deployed Multi AZ provides the ability to ensure database availability when deployed.

![ConnectPrivate](/images/diagram-wordpress-on-aws-cloud.png)

#### Amazon CloudFront
Amazon CloudFront is a content delivery network (CDN) service built for high-performance, secure user experience.

#### Auto Scaling Group
Auto Scaling Group is a group of EC2 Instances. This group can scale the number of EC2 Instance members according to the scaling policy you set.

#### Load Balancer
The Load Balancer is a tool that can distribute the traffic of exchanged data to AWS resources (specifically in this lab, EC2 Instances) in the Target Group.

#### Target Group
The Target Group is a group of AWS resource elements that will receive data traffic delivered and transported by the Load Balancer.

#### Amazon Relational Database Service (Amazon RDS)
Amazon RDS is an automated database operation service (Database-as-a-service) that allows you to automate the creation, operation, and scaling of a database. relational database on the AWS cloud computing platform.

#### Multiple Availability Zone (Multi-AZ)
Multi-AZ is a feature that allows you to deploy a synchronous backup copy of the original database on a DB instance in a different Availability Zone. If access to the original database is interrupted, the other synchronous backup will be used instead to ensure high availability for your database.