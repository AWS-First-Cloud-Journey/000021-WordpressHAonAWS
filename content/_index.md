+++
title = "Migration ShareNote with CloudEndure"
date = 2020
weight = 1
chapter = false
+++

# Migrate ShareNote with CloudEndure

This lab will guide you how to use CloudEndure to migrate an EC2 instance running your ShareNote application (include or not include MySQL) to another EC2 instance.

We will reuse the EC2 instance that we deploy the ShareNote application in the previous lab [Deploy ShareNote on Windows/Ubuntu Virtual Server]() as the source. The Source Machine can be a Linux machine or Windows machine.

#### Contents

We devided this lab into sections below:

1. [AWS Credential for CloudEndure](1-credentials/)
2. [Configure CloudEndure](2-config-cloudendure/)
3. [Install CloudEndure Agents](3-install-agent/)
4. [Configure Blueprint](4-blueprint/)
5. [Start Cutover](5-cutover/)
6. [Configure Security Group](6-security-group/)