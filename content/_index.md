+++
title = "Migration ShareNote with CloudEndure"
date = 2020
weight = 1
chapter = false
+++

# Migrate ShareNote with CloudEndure

This lab will guide you how to use CloudEndure to migrate an EC2 instance running your ShareNote application (include or not include MySQL) to another EC2 instance.

We will reuse the EC2 instance that we deploy an EC2 instance as the source. The Source Machine can be a Linux machine or Windows machine.

#### Contents

We devided this lab into sections below:
1. [Create an EC2 instance](1-create-ec2-instance/)
2. [AWS Credential for CloudEndure](2-credentials/)
3. [Configure CloudEndure](3-config-cloudendure/)
4. [Install CloudEndure Agents](4-install-agent/)
5. [Configure Blueprint](5-blueprint/)
6. [Start Cutover](6-cutover/)