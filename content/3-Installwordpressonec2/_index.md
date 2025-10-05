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

1. After connecting EC2 instance successfully. You will perform the following preparation steps to deploy the application:

- Install httpd service by copying the following command:

```bash
$ sudo dnf upgrade -y
$ sudo dnf install -y httpd
```

![wp](/images/3.connect/3.1.wp.png)
![wp](/images/3.connect/3.2.wp.png)

- Install php-mysql.

```bash
$ sudo dnf install -y php-mysqli
```

![wp](/images/3.connect/3.3.wp.png)

- Install php.

```
$ sudo dnf install -y php
```

![wp](/images/3.connect/3.4.wp.png)

- Enable httpd service and start it immediately.

```
$ sudo systemctl enable httpd --now
```

- Move to the directory where wordpress executes to proceed with download and installation.

```
$ cd /var/www/html/
$ ls
```

- Grant webserver write permissions to this directory

```
$ sudo chown -R apache:apache /var/www/html
$ sudo chmod -R 755 /var/www/html

```

- Create health file for ***health check*** later:

```
echo "OK" | sudo tee /var/www/html/health
```

- Download and install wordpress.

```
$ sudo wget https://wordpress.org/latest.tar.gz
$ sudo tar -xzf latest.tar.gz
```

![wp](/images/3.connect/3.4.3.wp.png)

- Check download and extract results.
```
$ ls
```

![wp](/images/3.connect/3.4.4.wp.png)

- Move into wordpress directory and check.
```
$ cd wordpress
$ ls
```

- Open web browser to access the public ipv4 dns address of ec2 webserver (if it doesn't work, try using **http**).
- Copy ipv4 dns public.

![wp](/images/3.connect/3.4.6.wp.png)

- Open browser with Public ipv4 dns and add `/wordpress/wp-admin/setup-config.php`.
- Click Let's go.

![wp](/images/3.connect/3.4.7.wp.png)

Set up basic parameters for wordpress
-	**Database Name:** `awsuser` (Name of the database created previously).
-	**Username:** `admin`.
-	**Password:** `dbpassword`.
-	**Database Host**: <Your Endpoint Database>.
-	**Table Preflix:** wp_.

![wp](/images/3.connect/3.5.wp.png)

- After submitting.

![wp](/images/3.connect/3.6.wp.png)

- Copy the data in the box and enter it into the **wp-config.php** file: 

```
$ sudo nano wp-config.php
```
- **Ctrl + Shift + v** to paste data into the file, then press **Ctrl + x** to exit, press **y** and press Enter to save. 

![wp](/images/3.connect/3.4.8.wp.png)

Select **run the installation** to proceed to the next step

![install-wordpress](/images/setupwordpress/install-wordpress-setup-13.png?featherlight=false&width=90pc)

After the installation is complete, proceed to login to wordpress admin

![install-wordpress](/images/setupwordpress/install-wordpress-setup-14.png?featherlight=false&width=90pc)

Successfully logged into the wordpress dashboard interface

![wp](/images/3.connect/3.9.wp.png)