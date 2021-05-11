---
title: "AWS Organization"
chapter: true
weight: 20
---

# AWS Organization

When using AWS Organizations, AWS Accounts are organized in Organizational Units (OUs). This allows you to manage groups of accounts as one unit. During the setup, AWS Control Tower created two OUs per default: `core` and `custom`

This lab covers the creation of your first Organizational Unit. You will use this to create your first workload-related AWS account. Per default, AWS Control Tower creates an additional OU for custom workloads (call `custom`), but for educational purposes you will create a new one.

## Create an OU

All operations concerning AWS Organizations must be made from the AWS Root Account. To create a new OU we have to do the following steps:

1. Use AWS Single Sign-On and access your AWS Root Account
1. Go to the [Control Tower Management Console](https://eu-central-1.console.aws.amazon.com/controltower/home/dashboard?region=eu-central-1)
1. Click on "Organizational Units" in the navigation bar
1. Use the "Add an OU" button to create a new Organization Unit
1. Choose a unique name for the OU (e.g. `workloads`) and click "Add"

[Screenshots]

When the newly created Organization Unit is configured in Control Tower it's time to create the first AWS account for the intended workload.

## Create a new AWS Account

One of the foundamental concepts of a multi-account AWS environment is to have a dedicated AWS account whenever possible. Therefore, you need to create a dedicated AWS Account for the example workload and assign the AWS Account to the `workloads` Organizational Unit you created before.

Since the goal is to establish a well-architected baseline for all AWS accounts, you should use AWS Control Tower Console to create a new AWS account. This will not only create a new AWS account, but will also ensure all configured guardrails are deployed to this new account as well.

Create a new AWS account:

1. Use AWS Single Sign-On and access your AWS Root Account
1. Go to the [Control Tower Management Console](https://eu-central-1.console.aws.amazon.com/controltower/home/dashboard?region=eu-central-1)
1. Select “Account factory” from the navigation bar
1. Click on “Enroll account”
1. Provide the needed details and select the `workloads` OU
1. Click on “Enroll account” to start the account creation process

[Screenshots account creation]

It will take some time until the new account is ready. You can check the status on the "Accounts" overview of the AWS Control Tower console.
