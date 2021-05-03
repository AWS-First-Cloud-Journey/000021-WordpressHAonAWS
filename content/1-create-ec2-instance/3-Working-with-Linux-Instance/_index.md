+++
title = "Using Linux Instance"
date = 2020-04-18T00:38:32+07:00
weight = 3
chapter = false
pre = "<b>1.1.3. </b>"
+++

> This lab shows how to create an Linux EC2 Instance using AWS Management Console.  

**Contents**
- [Step 1: Launch an instance](#step-1-launch-an-instance)
- [Step 2: Connect to your instance](#step-2-connect-to-your-instance)
- [Step 3: Clean up Linux instance](#step-3-clean-up-linux-instance)

#### Step 1: Launch an instance

---

> In this lab, we will launch a Linux instance using the AWS Management Console.  
> **Let's start!**

1. We will go to the **Amazon EC2 console** at https://console.aws.amazon.com/ec2/

2. To create an instance, click on **Launch Instance**.

![Launch an Instance](/images/1/2-2-launch-instance.png?width=90pc)

3. The **Choose an Amazon Machine Image (AMI)** page shows a list of Amazon Machine Images (AMIs), that serve as templates for your instance. Select an **HVM version of Amazon Linux 2**. 

![Select Linux AMI](/images/1/2-23-select-linux-ami.png?width=90pc)

4. On the **Choose an Instance Type** page, you can select the hardware configuration of your instance. Select the ```t2.micro``` type.

![Select Linux Instance Type](/images/1/2-24-select-instance-type-linux.png?width=90pc)

5. Select **Review and Launch** to let the wizard automatically config other settings as default.
6. On the **Review Instance Launch** page, under **Security Groups**, you'll see that the wizard created and selected a security group for you. You can use this security group, or alternatively you can select the security group that you created when getting set up using the following steps:
   1. Choose **Edit security groups**.
   2. On the **Configure Security Group** page, ensure that **Select an existing security group** is selected.
   3. Select your security group from the list of existing security groups, and then choose **Review and Launch**.
![Review Security Group](/images/1/2-25-review-security-group.png?width=90pc)
7. On the **Review Instance Launch** page, choose **Launch**.

![Review and Launch Instance](/images/1/2-26-review-linux-instance-config.png?width=90pc)

8. When prompted for a key pair, select **Choose an existing key pair**, then select the key pair that you created when getting set up.  
Alternatively, you can create a new key pair. **Select Create a new key pair**, enter a name for the key pair, and then choose **Download Key Pair**. This is the only chance for you to save the private key file, so be sure to download it. Save the private key file in a safe place. You'll need to provide the name of your key pair when you launch an instance and the corresponding private key each time you connect to the instance.
![Create Keypair for Linux instance](/images/1/2-27-create-linux-instance-keypair.png?width=90pc)
> **Warning**: 
> ```Don't``` select the Proceed without a key pair option. If you launch your instance without a key pair, then you ```can't connect``` to it.

9. When you are ready, select the acknowledgement check box, and then choose **Launch Instances**.
10.  A confirmation page lets you know that your instance is launching. Choose **View Instances** to close the confirmation page and return to the console.

![Successfully Launch Instance](/images/1/2-28-launch-linux-success.png?width=90pc)

11.  On the **Instances** screen, you can view the status of the launch. It takes a short time for an instance to launch. When you launch an instance, its initial state is pending. After the instance starts, its state changes to running and it receives a public DNS name. (If the **Public DNS (IPv4)** column is hidden, choose **Show/Hide Columns** (the gear-shaped icon) in the top right corner of the page and then select **Public DNS (IPv4)**.)
12.  It can take a few minutes for the instance to be ready so that you can connect to it. Check that your instance has passed its status checks; you can view this information in the **Status Checks** column.

![Linux Instance Information](/images/1/2-29-linux-instance-info.png?width=90pc)

#### Step 2: Connect to your instance

---

There are several ways to connect to your Linux instance.  
In this lab, we will try to connect to Linux instance by using **PuTTY on Windows** and **Windows PowerShell**.

**Connect to Linux instance by PuTTY on Windows**

---

1. Select the instance in Instance list then go to **Actions > Connect** 

![Connect to Instance](/images/1/2-30-connect-linux-instance.png?width=90pc)

1. Then in **Connect to your instance** dialog box, note the **Public DNS information**.

![Linux Instance Connect Information](/images/1/2-31-get-linux-instance-public-dns.png?width=90pc)

3. Open PuTTYGen to convert the keypair download when creating the instance (in ```.pem``` or ```.bib``` format) to ```.ppk``` format.
   1. In PuTTYGen, click Load to select the Key Pair downloaded. (If we can not see the file, please change the File type in Open dialog to ```All File (*.*)```)

![Load Created Keypair](/images/1/2-32-load-linux-keypair.png?width=50pc)

   2. Choose Save private key to save Key pair to ```.ppk``` format.

![Save Private Key](/images/1/2-33-save-linux-private-key.png?width=50pc)

4. Open PuTTY to connect to Linux instance:
   1. The **Host Name** should be ```ec2-user@<Public DNS>``` (List of username can be found in [General prerequisites for connecting to your instance](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/connection-prereqs.html))
   2. In PuTTY, navigate to **Connection > SSH > Auth** then select the converted private key.
   3. Finally, click Open to connect to instance
![Authentication configure](/images/1/2-34-athentication-configure.png?width=50pc)

![Connect to Linux Instance](/images/1/2-35-connecting-to-linux-instance.png?width=50pc)

1. If a dialog display about **PuTTY Security Alert**, click on Yes to accept the host key, put it to cache and continue to connect.

![Successfully Connect to Linux Instance](/images/1/2-36-successfully-ssh-linux-instance.png?width=50pc)

---
**Connect to Linux instance by Windows PowerShell**

---

1. Select the instance in Instance list then go to **Actions > Connect** 

![Connect to Instance](/images/1/2-30-connect-linux-instance.png?width=90pc)

1. Then in **Connect to your instance** dialog box, note the **Public DNS information**.

![Linux Instance Connect Information](/images/1/2-31-get-linux-instance-public-dns.png?width=90pc)

1. Open Windows PowerShell và connect with ec2
![connect](/images/1/2-37-connect-with-powershell.png?width=90pc)
#### Step 3: Clean up Linux instance

---

It will be the same as terminate a Windows Instance. For more details step, you can return to [Clean up Windows instance](../2-working-with-windows-instance/#step-3-clean-up-windows-instance)

**To terminate your instance**

---

1. In the navigation pane, choose **Instances**. In the list of instances, select the instance.
2. Choose **Actions > Instance State > Terminate**.
3. Choose **Yes, Terminate** when prompted for confirmation.

Amazon EC2 shuts down and terminates your instance. After your instance is terminated, it remains visible on the console for a short while, and then the entry is deleted.
![Delete](/images/1/2-38-delete-ec2.png?width=90pc)