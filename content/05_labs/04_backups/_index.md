---
title: "Automated Backups"
chapter: true
weight: 40
---

# Automated Backups

This lab covers the basic functionality of the **Automated Backups** feature of [superwerker]. Using [AWS Backup], all DynamoDB tables, EBS volumes, and RDS instances are secured with daily backups.

## DynamoDB

To create a new DynamoDB table, use the AWS DynamoDB Console:

1. Use AWS Single Sign-On and access your AWS Workload Account
1. Open the [AWS DynamoDB console](https://console.aws.amazon.com/dynamodb/home)
1. Click the blue “Create table" button
1. Choose a table name and configure at least a partition key
1. Create the table by clicking the “Create" button

[Screenshots of table create form]

After creating the table, you need to wait a few seconds before you can add items to the table. Select the "Items" tab for your table and click "Create Item" to add items to the DynamoDB table.

## Backup Configuration

The configuration for backup frequencies, is handled with `tags` for the specific AWS resource. For every resource type supported by [superwerker], an automation creates a tag called `superwerker:backup` and sets the initial value to `daily`.

> After a short period of time, the needed tag is visible when you select the `Tags` section for your DynamoDB table.

Currently, you can either use `daily` as the value or disable automated backups with setting the value to `none`.

[Screenshot of table tags]

To prevent any misconfiguration, [superwerker] uses AWS Tag Policies to enforce only supported values for the tag.

[Screenshot of table tags error with invalid option]

## AWS Backup

With the [superwerker] configuration in place, [AWS Backup] will create daily backups of your resources and only delete them after 30 ddays.

> Using "Backup Plans," every day at 5am (UTC) a new backup is created. You need to wait for the next day, to see the backup listed in [AWS Backup].

[Screenshot of AWS Backup]

[aws backup]: https://aws.amazon.com/backup/
[superwerker]: https://superwerker.cloud
