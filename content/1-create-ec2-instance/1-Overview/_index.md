+++
title = "Overview"
date = 2020-04-18T00:38:32+07:00
weight = 1
chapter = false
pre = "<b>1.1. </b>"
+++

The instance is an Amazon EBS-backed instance (meaning that the root volume is an EBS volume). You can either specify the Availability Zone in which your instance runs, or let Amazon EC2 select an Availability Zone for you. When you launch your instance, you secure it by specifying a key pair and security group. When you connect to your instance, you must specify the private key of the key pair that you specified when launching your instance.

![Deployment Overall Diagram](/images/1/overview_ec2.png)