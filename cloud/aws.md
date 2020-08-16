**Virtual Private Cloud (VPC)** is a virtual network dedicated to a single AWS account. It is logically isolated from other virtual networks in the AWS cloud, providing compute resources with security and robust networking functionality.


Each **region** is a separate geographic area. Each region has multiple, isolated locations (atleast 2) known as **Availability Zones**.

Regions:
US East (N. Virginia) - this is the region where new services launch first. This is also the region that goes down most often. :)

An **Availability Zone (AZ)** is a distinct location within an AWS Region engineered to be isolated from failures. Each Region comprises at least two AZs.

## Identity Access Management (IAM)

Identity Access Management (IAM) allows you to manage users and their level of access to the AWS Console.

- Centralized control of your AWS account.
- Shared Access to your AWS account.
- Granular Permissions
- Identity Federation (including Active Directory, Facebook, Linkedin, etc).
- Multifactor Authentication (username + password + code).
- Provide temporary access for users/devices and services where necessary. (Eg. a mobile-phone app is storing the data into your AWS account.)
- Allows to set up your own password rotation policy.
- Integrates with many different AWS services.
- Supports PCI DSS Compliance. (Eg. if you're taking credit card details need to be compliant with this framework.)

**IAM** comparises of:
1. *Users*
2. *Groups*
3. *Policies*: documents in JSON format; giving permissions as to what a User/Group/Role is able to do.
4. *Roles*: create roles and assign them to AWS Resources.

When you are handling/editing the IAM for your AWS account, the region always shows "Global". This is due to the fact that your IAM related configuration is global and not tied to any specific region.

**IAM learnings:**

- IAM is universal. It does not apply to regions.
- "Root account" is the account created when setting up a new AWS account using your email. It has complete Admin access. (GOD mode.)
- Always setup **Multifactor Authentication** (MFA) on your root account.
- New users have **NO permissions** when first created.
- New users can be assigned **Access Key ID** and **Secret Access Keys** after creation to access AWS resources programatically. (In addition to the AWS console access).
- *Access Keys* are not same as a password. You can't use it to login to the AWS Console. It can be used to access AWS via APIs and Command Line.
- You can only view *Access Keys* once. If you loose it, you will have to regenerate them.


# How to create a billing alarm.

1. Services --> Management & Governance --> CloudWatch.
2. CloudWatch Console --> from the left Menu --> Alarms --> Billing.
3. Press the "create alarm" button (on the bottom of the screen).
4. From the "Condition" screen, set:
    - Threshold Type = "Static"
    - Condition = "Greater than"
    - Threshold value = "$10". \
press "**Next**".
5. From the "Notification" screen, set:
    - Alarm state trigger = In alarm
    - SNS (Simple Notification Service) topic = Create new topic
    - topic name = "billing_alarm_over_10"
    - email endpoints = "\<email\>"
    - Click "create topic". \
    This creates the new topic and it gets automatically selected and the radio button sets to "Select an existing SNS topic".
    - Click "**Next**".
6. From the "Name and description" screen, set:
    - Alarm name = "Billing Alarm over $10"
    - Description = "Generate alarm if estimated billing goes over $10"
7. From the preview windows, scroll down (confirm all your configuration) and press "**Create alarm**".

You'll now be taken to the "Billing Alarms" screen where you'll see "Pending Confirmation" action. You need to accept the subscription to this alarm from your email.

# S3 - Simple Storage Service

- provides secure, durable highly-scalable **object storage** (flat files - documents, pictures, etc).
    Object consists of:
    - Key - name of the object.
    - Value - data (made up of sequence of bytes).
    - Version ID - for versioning (to keep multiple versions of an object).
    - Metadata (classification - say: HR, Finance, etc.)
    - Subresources (Access Control Lists; Torrent)
- provides web services interface to store and retrieve any amount of data.
- Files can be from 0B to 5TB. Unlimited storage.
- Files are stored in *Buckets*. (A Bucket is logically similar to a "folder").

## S3 Buckets

- universale namespace (has to be globally unique).

Example-1: A Bucket *acloudguru* is created in the default (`N. Virginia`) region.
```
URL: https://acloudguru.s3.amazonaws.com/
```

Example-2: A Bucket *acloudguru* is created in the `EU-West-1` region.
```
URL: https://acloudguru.eu-west-1.amazonaws.com/
```
- if object/file upload was successful, it returns `HTTP 200 OK`.

## S3 Data Consistency

- `Read` after `Write` consistency for `PUT`s of new Objects (i.e. following an upload/`PUT` of a new object, there can be a successful `GET` operation immediately after.)

- Eventual Consistency for overwrite `PUT`s and `DELETE`s (can take time to propogate i.e. after a `PUT` of version-2 of an Object, the immediate `GET` might return version-2 or might still return version-1 of the object but eventually it will get consistent and always return version-2. Same for `DELETE` operation followed by a `GET` - you might still be returned the object until things get consistent and you get a `HTTP 404`).

## S3 Guarantees

- 99.99% availability for the S3 platform.
- 99.999999999% (11 x 9s) durability of S3 information (probability of your object getting *lost* i.e. 1 in a Billion [1,000,000,000] objects).

# Links and References:
(a) AWS Monthly Calculator: \
https://calculator.s3.amazonaws.com/index.html


