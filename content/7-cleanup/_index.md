---
title : "Clean up resources"
date : "2025-10-02"
weight : 7
chapter : false
pre : "<b>7. </b>"
---

We will take the following steps to delete the resources we created in this exercise.

#### Remove Auto Scaling Group:

- Access EC2 Management Console
- On the left navigation bar, select Auto Scaling Groups
- Select Auto Scaling Group related to the lab.
- Click Delete
- Type delete in the empty box and press delete

#### Remove Load Balancer:
- Access EC2 Management Console
- On the left navigation bar, select Load Balancers
- Select Load Balancer related to the lab.
- Click Actions.
- Click Delete.
#### Remove Target Group:
- Access EC2 Management Console
- On the left navigation bar, select Target Groups
- Select Target Group related to the lab.
- Click Actions.
- Click Delete.
- Click Yes, delete
#### Remove Launch Template:
- Access EC2 Management Console
- On the left navigation bar, select Launch Templates
- Select Launch Template related to the lab.
- Click Actions.
- Click Delete template
- Type delete in the empty box and press delete

#### Delete AMI:
- Access EC2 Management Console
- On the left navigation bar, select AMIs
- Select the AMI related to the lab.
- Click Actions.
- Click Deregister.
- Click Continue.
#### Terminate EC2 instance:
- Access EC2 Management Console
- On the left navigation bar, select Instances
- Select all EC2 Instances related to the lab.
- Click Actions.
- Click Manage Instance State.
- Select Terminate.
- Click Change State
#### Delete DB Instance
- Access the RDS Management Console
- On the left navigation bar, select Databases
- Select all DB Instances related to the lab.
- Click Actions.
- Click Delete
- Uncheck Create final snapshot? and select I acknowledge that upon instance deletion, automated backups, including system snapshots and point-in-time recovery, will no longer be available
- Type delete me in the empty box.
- Click Delete
#### Remove VPC + subnet + security group:
- Access VPC Management Console
- On the left navigation bar, select Your VPCs
- Select VPC related to Lab
- Click to select Action
- Click Delete VPC
- Type delete in the empty box
- Click Delete
#### Remove Cloudfront Distribution
- Access Cloudfront Management Console
- On the left navigation bar, select Distribution
- Select Distribution related to the lab
- Select Delete