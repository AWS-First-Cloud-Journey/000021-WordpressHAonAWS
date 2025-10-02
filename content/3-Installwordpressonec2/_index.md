---
title : "Installing wordpress on EC2"
date : "2025-10-02"
weight : 3
chapter : false
pre : " <b> 3. </b> "
---
{{% notice note %}}
Details of [ EC2 Instance connection ](000004.awsstudygroup.com/4-launchlinuxinstance/4.2-connectlinuxinstance/)
{{% /notice %}}

1. After connecting EC2 instance successfully. You will take the following steps to prepare to deploy the application:

- Install httpd service by copying the following command:

```
sudo yum install -y httpd
```

![install-wordpress](/images/setupwordpress/install-wordpress-setup-0.png?featherlight=false&width=90pc)

- Install php-mysql

```
sudo yum install php-mysql -y
```

![install-wordpress](/images/setupwordpress/install-wordpress-setup-1.png?featherlight=false&width=90pc)

- Install php7.3

```
sudo amazon-linux-extras install -y php7.3
```
![install-wordpress](/images/setupwordpress/install-wordpress-setup-2.png?featherlight=false&width=90pc)

Move the directory to where wordpress executes to download and install
```
$ cd /var/www/html/
$ ls
```
![install-wordpress](/images/setupwordpress/install-wordpress-setup-3.png?featherlight=false&width=90pc)

- Download and install wordpress
```
$ wget https://wordpress.org/latest.tar.gz
$ tar -xzf latest.tar.gz
```

![install-wordpress](/images/setupwordpress/install-wordpress-setup-4.png?featherlight=false&width=90pc)

- Check download and extract results
```
$ ls
```

![install-wordpress](/images/setupwordpress/install-wordpress-setup-5.png?featherlight=false&width=90pc)

- Move into wordpress folder and check
```
$ cd wordpress
$ ls
```
![install-wordpress](/images/setupwordpress/install-wordpress-setup-6.png?featherlight=false&width=90pc)

Open a web browser to access the public ipv4 dns address of the ec2 webserver
- Copy ipv4 dns public

![install-wordpress](/images/setupwordpress/install-wordpress-setup-7.png?featherlight=false&width=90pc)

- Open browser with Public ipv4 dns and add /wordpress/wp-admin/setup-config.php

![install-wordpress](/images/setupwordpress/install-wordpress-setup-8.png?featherlight=false&width=90pc)

Set up basic parameters for wordpress
- Database Name: awsuser (Name of previously created database)
- Username: admin
- Password: dbpassword
- Database Host: Your Endpoint Database
- Table Preflix: wp_

![install-wordpress](/images/setupwordpress/install-wordpress-setup-9.png?featherlight=false&width=90pc)

After submitting

![install-wordpress](/images/setupwordpress/install-wordpress-setup-10.png?featherlight=false&width=90pc)

Rename the file wp-config-sample.php to file wp-config.php
```
$ mv wp-config-sample.php wp-config.php
```

![install-wordpress](/images/setupwordpress/install-wordpress-setup-11.png?featherlight=false&width=90pc)

Delete the data in the wp-config.php file and copy the information in the previous step into the wp-config.php file.
```
$ cat > wp-config.php
$ nano wp-config.php
```

![install-wordpress](/images/setupwordpress/install-wordpress-setup-12.png?featherlight=false&width=90pc)

Select run the installation to proceed to the next step

![install-wordpress](/images/setupwordpress/install-wordpress-setup-13.png?featherlight=false&width=90pc)

After the installation is complete, login to wordpress admin

![install-wordpress](/images/setupwordpress/install-wordpress-setup-14.png?featherlight=false&width=90pc)

Successfully logged in to the wordpress dashboard interface

![install-wordpress](/images/setupwordpress/install-wordpress-setup-15.png?featherlight=false&width=90pc)