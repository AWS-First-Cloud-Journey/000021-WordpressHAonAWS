+++
title = "Using Windows Instance"
date = 2020-04-18T00:38:32+07:00
weight = 2
chapter = false
pre = "<b>1.2. </b>"
+++

> This lab shows how to create an Windows EC2 Instance using AWS Management Console.

**Contents:**
- [Step 1: Launch an instance](#step-1-launch-an-instance)
- [Step 2: Connect to your instance](#step-2-connect-to-your-instance)
- [Step 3: Clean up Windows instance](#step-3-clean-up-windows-instance)

#### Step 1: Launch an instance

---

> In this lab, we will launch a Windows instance using the AWS Management Console. In addition, there are other posible options for create a new instance (More details on [Launching an Instance](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/launching-instance.html)).  
> **Let's start!**

1. Firstly, we will go to the **Amazon EC2 console** at https://console.aws.amazon.com/ec2/.

2. To create an instance, click on **Launch Instance**.

![Launch an Instance](/images/1/2-2-launch-instance.png?width=90pc)

3. The **Choose an Amazon Machine Image (AMI)** page shows a list of Amazon Machine Images (AMIs). Select the AMI named **Windows Server 2019 Base** or later.

![Select Windows AMI](/images/1/2-3-select-windows-ami.png?width=90pc)

4. Then, On the **Choose an Instance Type** page, you can select the hardware configuration of the instance. Select the **t2.micro** instance type.

![Select Instance Type](/images/1/2-4-select-instance-type-windows.png?width=90pc)

5. Select **Review and Launch** to let the wizard automatically config other settings as default.
6. On the **Review Instance Launch** page, under **Security Groups**, you'll see that the wizard created and selected a security group for you. You can use this security group, or alternatively you can select the security group that you created when getting set up using the following steps:
   1. Choose **Edit security groups**.
   2. On the **Configure Security Group** page, ensure that **Select an existing security group** is selected.
   3. Select your security group from the list of existing security groups, and then choose **Review and Launch**.

![Edit Security Groups](/images/1/2-5-config-ec2-sg.png?width=90pc)

7. On the **Review Instance Launch** page, choose **Launch**.

![Review and Launch Instance](/images/1/2-6-review-windows-instance-config.png?width=90pc)

8. When prompted for a key pair, select **Choose an existing key pair**, then select the key pair that you created when getting set up.

![Select Keypair for Instance](/images/1/2-7-select-keypair-windows-instance.png?width=90pc)

Alternatively, you can create a new key pair. Select **Create a new key pair**, enter a name for the key pair, and then choose **Download Key Pair**. This is **the only chance** for you to save the private key file, so be sure to download it. Save the private key file in a safe place. You'll need to provide the name of your key pair when you launch an instance and the corresponding private key each time you connect to the instance.

![Create Keypair for Instance](/images/1/2-8-create-windows-instance-keypair.png?width=90pc)

> **Warning**: 
> **```Don't```** select the **Proceed** without a key pair option. If you launch your instance without a key pair, then you can't connect to it.

9. When you are ready, select the **acknowledgement check box**, and then choose **Launch Instances**.

10. A confirmation page lets you know that your instance is launching. Choose **View Instances** to close the confirmation page and return to the console.

![Successfully Launch Instance](/images/1/2-9-launch-windows-success.png?width=90pc)

11. On the **Instances** screen, you can view the status of the launch. It takes a short time for an instance to launch. When you launch an instance, its initial state is pending. After the instance starts, its state changes to running and it receives a public DNS name. (If the **Public DNS (IPv4)** column is hidden, choose **Show/Hide Columns** (the gear-shaped icon) in the top right corner of the page and then select **Public DNS (IPv4)**.)
12. It can take a few minutes for the instance to be ready so that you can connect to it. Check that your instance has passed its status checks; you can view this information in the **Status Checks** column.

![Windows Instance Information](/images/1/2-10-windows-instance-info.png?width=90pc)

#### Step 2: Connect to your instance

---

To connect to a Windows instance, you must retrieve the initial administrator password (see step 2 below) and then specify this password when you connect to your instance using Remote Desktop.  
> **Notes**:  
> - The name of the administrator account depends on the language of the operating system. For example, for English, it's Administrator, for French it's Administrateur, and for Portuguese it's Administrador.  
> - The license for the Windows Server operating system (OS) allows two simultaneous remote connections for administrative purposes. The license for Windows Server is included in the price of your Windows instance. If you need more than two simultaneous remote connections, you must purchase a Remote Desktop Services (RDS) license. If you attempt a third connection, an error occurs.

**To connect to your Windows instance using an RDP client**

---

1. In the **Amazon EC2 console**, select the instance, and then choose **Connect** in **Actions menu**.

![Choose Connect](/images/1/2-11-connect-windows-instance.png?width=90pc)


2. In the **Connect To Your Instance** dialog box, choose **Get Password** (it will take a few minutes after the instance is launched before the password is available).

![Decrypt Password](/images/1/2-12-get-windows-instance-admin-password.png?width=90pc)

3. Choose **Browse** and navigate to the private key file you created when you launched the instance. Select the file and choose **Open** to copy the entire contents of the file into the **Contents** field.

![Select Keypair for Decryption](/images/1/2-13-select-keypair-to-decrypt-admin-password.png?width=90pc)

4. Choose **Decrypt** Password. The console displays the default administrator password for the instance in the **Connect To Your Instance** dialog box, replacing the link to **Get Password** shown previously with the actual password.

![Successfully Decrypt Password](/images/1/2-14-successfully-get-password.png?width=90pc)

1. Record the default administrator password, or copy it to the clipboard. You need this password to connect to the instance. 
2. Choose **Download Remote Desktop** File. Your browser prompts you to either open or save the ```.rdp``` file. Choose Save to download the file to local machine.
3. Opened the downloaded ```.rdp``` file, you'll see the **Remote Desktop Connection** dialog box.
4. You may get a warning that the publisher of the remote connection is unknown. You can continue to connect to your instance.

![Accept Publisher](/images/1/2-15-connecting-to-windows-instance.png?width=30pc)

9.  When prompted, log in to the instance, using the administrator account for the operating system and the password that you recorded or copied previously. If your Remote Desktop Connection already has an administrator account set up, you might have to choose the Use another account option and type the user name and password manually.

> **Note**: 
> Sometimes copying and pasting content can corrupt data. If you encounter a "Password Failed" error when you log in, try typing in the password manually.

![Login to Windows Instance](/images/1/2-16-login-windows-instance.png?width=30pc)

10. Due to the nature of self-signed certificates, you may get a warning that the security certificate could not be authenticated. Simply choose **Yes** or **Continue** to continue.

![Accept Certificate](/images/1/2-17-accept-cerificate-windows-instance.png?width=30pc)

11. The desktop of Windows instance will shows after the connection is established.

![Successfully Connect to Windows Instance](/images/1/2-18-successfully-rdp-windows-instance.png?width=90pc)

{{% notice warning %}}
If there is an error connecting to EC2, check the Security Group Inbound rule assigned to EC2.\
Access EC2 Console => Security Group.\
Choose security group assigned to EC2.\
Choose **Action | Edit Inbound rules**
![Choose Edit Inbound rule Security Group](/images/1/2-19-choose-edit-inbound-rule.png?width=90pc)
Change **Source** to **Anywhere** and choose **Save rules**
![Change Source to Anywhere](/images/1/2-20-change-source-to-anywhere.png?width=90pc)

#### Step 3: Clean up Windows instance

---

After you've finished with the instance that you created for this lab, you should clean up by terminating the instance.

> **Important**: 
> Terminating an instance effectively deletes it; you can't reconnect to an instance after you've terminated it.

If you launched an instance that is not within the AWS Free Tier, you'll stop incurring charges for that instance as soon as the instance status changes to shutting down or terminated. If you'd like to keep your instance for later, but not incur charges, you can stop the instance now and then start it again later. For more information, see Stopping Instances.

**To terminate your instance**

---

1. In the navigation pane, choose **Instances**. In the list of instances, select the instance.
2. Choose **Actions > Instance State > Terminate**.

![Terminate an Instance](/images/1/2-21-terminate-windows-instance.png?width=90pc)

3. Choose **Yes, Terminate** when prompted for confirmation.

![Instance terminating confirmation](/images/1/2-22-terminate-windows-instance-confirm.png?width=90pc)

Amazon EC2 shuts down and terminates your instance. After your instance is terminated, it remains visible on the console for a short while, and then the entry is deleted.
