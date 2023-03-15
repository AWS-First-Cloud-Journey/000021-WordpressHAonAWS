---
title : "Create Cloudfront for Web Server"
date : "`r Sys.Date()`"
weight : 6
chapter : false
pre : "<b>6. </b>"
---


1. Access the AWS Management Console
- Find Cloudfront
- Choose Cloudfront

![cloudfront](/images/setupcloudfront/setup-cloud-front-01.png?featherlight=false&width=90pc)

2. In the Cloudfront . interface
- Select Create a Cloudfront Distribution

![cloudfront](/images/setupcloudfront/setup-cloud-front-02.png?featherlight=false&width=90pc)


3. In the Create . interface
- Origin domain select Load Balancer domain

![cloudfront](/images/setupcloudfront/setup-cloud-front-03.png?featherlight=false&width=90pc)

4. Next leave everything as default and select Create distribution

![cloudfront](/images/setupcloudfront/setup-cloud-front-04.png?featherlight=false&width=90pc)

5. After successfully creating Cloudfront Distribution, the initialization process takes about 5 minutes.
- Save the Distribution Domain Name value to proceed with the installation in the next step


![cloudfront](/images/setupcloudfront/setup-cloud-front-05.png?featherlight=false&width=90pc)

6. In WordPress wp-admin interface
- Select Plugins
- Select Add New

![cloudfront](/images/setupcloudfront/setup-cloud-front-06.png?featherlight=false&width=90pc)

7. In the WordPress Plugin interface
- Type in the search box: WP Faster Cache
- Select Install now

![cloudfront](/images/setupcloudfront/setup-cloud-front-07.png?featherlight=false&width=90pc)