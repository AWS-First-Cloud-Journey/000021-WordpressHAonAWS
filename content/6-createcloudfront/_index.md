---
title: "Create Cloudfront for Web Server"
date: "2025-10-02"
weight: 6
chapter: false
pre: "<b>6. </b>"
---

1. Access **AWS Management Console**

   - Find **Cloudfront**
   - Select **Cloudfront**

![cf](/images/6.clean/6.1.png)

2. In the **Cloudfront** interface

   - Select **Create a Cloudfront Distribution**

![cf](/images/6.clean/6.2.png)

3. In the **Create** interface

   - **Distribute Name** enter `Webserver`
   - Select **Next**

![cf](/images/6.clean/6.3.png)

4. In the **Specify Origin** interface
   - Select **Elastic Load Balancing**
   - In the **Origin** section, **Elastic Load Balancing origin** enter <Load Balancer domain> created previously.
   - Path enter `/wordpress`
   - In the Settings section select **Customize origin settings**
   - **Protocol** select **Only HTTP**

![cf](/images/6.clean/6.4.png)
![cf](/images/6.clean/6.4.1.png)

5. In the **Enable Security** interface click **Next**

![cf](/images/6.clean/6.5.png) 5. In the **Review and create** interface click **Create distribution**

![cf](/images/6.clean/6.6.png)

6. In the **Wordpress wp-admin** interface

   - Select **Plugin**
   - Select **Add New**

![cf](/images/6.clean/6.7.png)

7. In the **Plugin** interface of **Wordpress**

   - Type in the search box: `WP Faster Cache`
   - Select `Install now`

![cf](/images/6.clean/6.8.png)

8. After successful installation, return to the **Plugin** interface
   - Select **Active**
   - Select **Plugin**
   - Find **WP Faster Cache** and select **Setting**

![cf](/images/6.clean/6.9.png)

9. In the **WP Faster Cache** interface
   - Select **CDN** on the toolbar
   - Then select **Other CDN Providers**

![cf](/images/6.clean/6.10.png)

10. A dialog box appears, proceed to enter
    - CDN Url: <Cloudfront distribution address you just created in the previous step>
    - Origin Url: <Load Balancer DNS>

![cf](/images/6.clean/6.11.png)

11. Continue to select **Next** in the following steps until **Finish**

![cf](/images/6.clean/6.15.png)

12. After setup is complete

![cf](/images/6.clean/6.16.png)

The process of installing **CDN** for **Wordpress** is now complete.
