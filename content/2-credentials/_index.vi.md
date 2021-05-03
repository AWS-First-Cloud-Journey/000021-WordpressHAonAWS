+++
title = "Tạo AWS Credential"
date = 2020
weight = 1
chapter = false
pre = "<b>1. </b>"
+++

**Nội dung**
- [Tạo IAM Policy cho CloudEndure](#tạo-iam-policy-cho-cloudendure)
- [Tạo IAM User và Credential cho CloudEndure](#tạo-iam-user-và-credential-cho-cloudendure)

#### Tạo IAM Policy cho CloudEndure

**Bước 1:** Từ **AWS Management Console**, truy cập dịch vụ **IAM** thông qua thanh điều hướng **Services**.

![IAM Policy](../../../images/2/1.png?width=90pc)

**Bước 2:** Ở menu bên trái của **IAM Console**, chọn **Policies**.

**Bước 3:** Ở trang **Polices**, chọn **Create Policy**.

**Bước 4:** Ở trang tạo **Policy**, chọn tab **JSON**.
![Create Policy](../../../images/2/2.png?width=90pc)
**Bước 5:** Sao chép đoạn JSON từ trang sau [CloudEndure IAM Policy](https://docs.cloudendure.com/Content/IAMPolicy.json)

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Sid": "VisualEditor0",
      "Effect": "Allow",
      "Action": "ec2:CreateTags",
      "Resource": "arn:aws:ec2:*:*:*/*",
      "Condition": {
        "StringEquals": {
          "ec2:CreateAction": "RunInstances"
        }
      }
    },
    {
      "Sid": "VisualEditor1",
      "Effect": "Allow",
      "Action": "ec2:CreateTags",
      "Resource": "arn:aws:ec2:*:*:*/*",
      "Condition": {
        "StringEquals": {
          "ec2:CreateAction": "CreateVolume"
        }
      }
    },
    {
      "Sid": "VisualEditor2",
      "Effect": "Allow",
      "Action": [
        "ec2:RevokeSecurityGroupIngress",
        "ec2:DetachVolume",
        "ec2:AttachVolume",
        "ec2:DeleteVolume",
        "ec2:TerminateInstances",
        "ec2:StartInstances",
        "ec2:RevokeSecurityGroupEgress",
        "ec2:StopInstances"
      ],
      "Resource": [
        "arn:aws:ec2:*:*:dhcp-options/*",
        "arn:aws:ec2:*:*:instance/*",
        "arn:aws:ec2:*:*:volume/*",
        "arn:aws:ec2:*:*:security-group/*"
      ],
      "Condition": {
        "StringLike": {
          "ec2:ResourceTag/Name": "CloudEndure*"
        }
      }
    },
    {
      "Sid": "VisualEditor3",
      "Effect": "Allow",
      "Action": [
        "ec2:RevokeSecurityGroupIngress",
        "ec2:DetachVolume",
        "ec2:AttachVolume",
        "ec2:DeleteVolume",
        "ec2:TerminateInstances",
        "ec2:StartInstances",
        "ec2:RevokeSecurityGroupEgress",
        "ec2:StopInstances"
      ],
      "Resource": [
        "arn:aws:ec2:*:*:dhcp-options/*",
        "arn:aws:ec2:*:*:instance/*",
        "arn:aws:ec2:*:*:volume/*",
        "arn:aws:ec2:*:*:security-group/*"
      ],
      "Condition": {
        "StringLike": {
          "ec2:ResourceTag/CloudEndure creation time": "*"
        }
      }
    },
    {
      "Sid": "VisualEditor4",
      "Effect": "Allow",
      "Action": [
        "ec2:DisassociateAddress",
        "ec2:CreateDhcpOptions",
        "ec2:AuthorizeSecurityGroupIngress",
        "ec2:DeregisterImage",
        "ec2:DeleteSubnet",
        "ec2:DeleteSnapshot",
        "ec2:ModifySnapshotAttribute",
        "ec2:ModifyVolumeAttribute",
        "ec2:CreateVpc",
        "ec2:AttachInternetGateway",
        "ec2:GetConsoleScreenshot",
        "ec2:GetConsoleOutput",
        "elasticloadbalancing:DescribeLoadBalancer*",
        "ec2:CreateRoute",
        "ec2:CreateInternetGateway",
        "ec2:CreateSecurityGroup",
        "ec2:CreateSnapshot",
        "ec2:ModifyVpcAttribute",
        "ec2:ModifyInstanceAttribute",
        "ec2:ReleaseAddress",
        "ec2:AuthorizeSecurityGroupEgress",
        "ec2:AssociateDhcpOptions",
        "ec2:ImportKeyPair",
        "ec2:CreateTags",
        "ec2:RegisterImage",
        "ec2:ModifyNetworkInterfaceAttribute",
        "ec2:AssociateRouteTable",
        "ec2:CreateRouteTable",
        "ec2:DetachInternetGateway",
        "iam:ListInstanceProfiles",
        "ec2:AllocateAddress",
        "ec2:ReplaceNetworkAclAssociation",
        "ec2:CreateVolume",
        "kms:ListKeys",
        "ec2:Describe*",
        "ec2:DeleteVpc",
        "iam:GetUser",
        "ec2:CreateSubnet",
        "ec2:AssociateAddress",
        "ec2:DeleteKeyPair",
        "ec2:CreateNetworkAclEntry"
      ],
      "Resource": "*"
    },
    {
      "Sid": "MigrationHubConfig",
      "Effect": "Allow",
        "Action": [
        "mgh:GetHomeRegion"
      ],
      "Resource": "*"
    },
    {
      "Sid": "VisualEditor5",
      "Effect": "Allow",
        "Action": [
        "ec2:RevokeSecurityGroupIngress",
        "mgh:CreateProgressUpdateStream",
        "kms:Decrypt",
        "kms:Encrypt",
        "ec2:RevokeSecurityGroupEgress",
        "ec2:DeleteDhcpOptions",
        "ec2:RunInstances",
        "kms:DescribeKey",
        "kms:CreateGrant",
        "ec2:DeleteNetworkAclEntry",
        "kms:ReEncrypt*",
        "kms:GenerateDataKey*"
      ],
      "Resource": [
        "arn:aws:mgh:*:*:progressUpdateStream/*",
        "arn:aws:ec2:*:*:subnet/*",
        "arn:aws:ec2:*:*:key-pair/*",
        "arn:aws:ec2:*:*:dhcp-options/*",
        "arn:aws:ec2:*:*:instance/*",
        "arn:aws:ec2:*:*:volume/*",
        "arn:aws:ec2:*:*:security-group/*",
        "arn:aws:ec2:*:*:network-acl/*",
        "arn:aws:ec2:*:*:placement-group/*",
        "arn:aws:ec2:*:*:vpc/*",
        "arn:aws:ec2:*:*:network-interface/*",
        "arn:aws:ec2:*::image/*",
        "arn:aws:ec2:*:*:snapshot/*",
        "arn:aws:kms:*:*:key/*"
      ]
    },
    {
      "Sid": "VisualEditor6",
      "Effect": "Allow",
      "Action": [
        "ec2:CreateTags",
        "mgh:ImportMigrationTask",
        "mgh:AssociateCreatedArtifact",
        "mgh:NotifyMigrationTaskState",
        "mgh:DisassociateCreatedArtifact",
        "mgh:PutResourceAttributes"
      ],
      "Resource": [
        "arn:aws:mgh:*:*:progressUpdateStream/*/migrationTask/*",
        "arn:aws:ec2:*:*:subnet/*",
        "arn:aws:ec2:*::network-interface/*",
        "arn:aws:ec2:*:*:dhcp-options/*",
        "arn:aws:ec2:*::snapshot/*",
        "arn:aws:ec2:*:*:security-group/*",
        "arn:aws:ec2:*::image/*"
      ]
    },
    {
      "Sid": "VisualEditor7",
      "Effect": "Allow",
      "Action": "ec2:Delete*",
      "Resource": [
        "arn:aws:ec2:*:*:route-table/*",
        "arn:aws:ec2:*:*:dhcp-options/*",
        "arn:aws:ec2:*:*:instance/*",
        "arn:aws:ec2:*:*:volume/*",
        "arn:aws:ec2:*:*:security-group/*",
        "arn:aws:ec2:*:*:internet-gateway/*"
      ],
      "Condition": {
        "StringLike": {
          "ec2:ResourceTag/Name": "CloudEndure*"
        }
      }
    },
    {
      "Sid": "VisualEditor8",
      "Effect": "Allow",
      "Action": "ec2:Delete*",
      "Resource": [
        "arn:aws:ec2:*:*:route-table/*",
        "arn:aws:ec2:*:*:dhcp-options/*",
        "arn:aws:ec2:*:*:instance/*",
        "arn:aws:ec2:*:*:volume/*",
        "arn:aws:ec2:*:*:security-group/*",
        "arn:aws:ec2:*:*:internet-gateway/*"
      ],
      "Condition": {
        "StringLike": {
          "ec2:ResourceTag/CloudEndure creation time": "*"
        }
      }
    }
  ]
}
```

**Bước 6:** Trên **IAM Console**, xoá tất cả nội dung đang hiện thị trên trình soạn thảo, sau đó dán đoạn JSON ở bước trước vào. 

![IAM Policy](../../../images/2/3.png?width=90pc)

**Bước 7:** Chọn **Review policy**.
![IAM Policy](../../../images/2/4.png?width=90pc)
**Bước 8:** Thiết lập các thông tin như sau:
   - Name: Đặt tên cho policy (VD: **AWS-CloudEndure**).
   - Description: Nhập mô tả (VD: **Sample AWS-CloudEndure policy**). 

![IAM Policy](../../../images/2/5.png?width=90pc)

**Bước 9:** Chọn **Create policy**.


#### Tạo IAM User và Credential cho CloudEndure

**Bước 1:** Ở menu bên trái của **IAM Console**, chọn **Users**. 
![Create User](../../../images/2/6.png?width=90pc)
**Bước 2:** Ở trang **Users**, chọn **Add user**.

**Bước 3:** Ở trang **Create User**:
   - Username: Điền tên user 
   - Access type: Chọn **Programmatic access**.

**Bước 4:** Chọn **Next: Permissions**.
![Create User](../../../images/2/7.png?width=90pc)
**Bước 5:** Chọn **Attach existing policies directly**.

![Create User](../../../images/2/8.png?width=90pc)

**Bước 6:** Ở ô **Search**, điền **AWS-CloudEndure**, sau đó chọn policy **AWS-CloudEndure** bằng cách nhấn vào ô vuông bên cạnh.

**Bước 7:** Chọn **Next: Tags**.
![Create User](../../../images/2/9.png?width=90pc)

**Bước 8:** Chọn **Next: Review**.
![Create User](../../../images/2/10.png?width=90pc)

**Bước 9:** Chọn **Create User**. 

**Bước 10:** Chọn **Download .csv**. Lưu trữ file tải về ở vị trí an toàn, ta sẽ sử dụng file này ở các bước sau.
![Create User](../../../images/2/11.png?width=90pc)

**Bước 11:** Chọn **Close**. 
