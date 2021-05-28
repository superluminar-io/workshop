---
title: "Example Workload"
description: "Lab Description for SEO"
chapter: true
weight: 30
---

# Example Workload

This lab covers a basic example workload (using an S3 bucket) in the AWS account created in [the previous lab](/05_labs/02_org_setup.html). 

## Workload

To showcase the benefits of a unified AWS environment, you will create an S3 bucket with the default configuration and intentional mistakes. The bucket could - for instance - be used to store internal files or public assets for a static website.

Using this example, a potential workload owner needs to be notified, that an insecure configuration of an AWS resource was applied. Regardless if the configuration is accidental or intended, using [superwerker] will ensure the same level of security and configuration for AWS resources across your AWS accounts.

## Create the S3 bucket

To create a new S3 Bucket, use the AWS S3 Console:

1. Use AWS Single Sign-On and access your AWS Workload Account
1. Open the [AWS S3 console](https://s3.console.aws.amazon.com/s3/home)
1. Click the orange “Create bucket” button
1. Choose a name and a region for the bucket.\
   _The bucket name needs to be unique (not just in your AWS account)_
1. Keep the default settings for everything else. \
   _Especially: do not enable “Server-side encryption”._
1. Create the bucket by clicking the “Create bucket” button

[Screenshots of bucket create form]

Now that you have a new S3 bucket without server-side encryption, let’s check if there are any security warnings, that can help us to mitigate this risk.

## Security Notification via Security Hub

When using [superwerker], AWS Security Hub and AWS Config are enabled by default. These services make sure your resources in AWS match the required configuration schema:

- AWS Config checks continuously all AWS resource to match a set of rules
- AWS Security Hub aggregate all security-related notifications in a dashboard

Now you need to check if the misconfiguration (_Using unencrypted S3 buckets_) was already noticed. To check the current security issues in the workload account use Security Hub:

1. Use AWS Single Sign-On and access your AWS Workload Account
1. Open the [Security Hub console](https://eu-central-1.console.aws.amazon.com/securityhub/home?region=eu-central-1#/summary)
1. Select “Findings” from the navigation bar
1. Locate the finding related to the new S3 bucket in the list \
   _It might take a couple of minutes until it appears_
1. You can take a closer look at the finding and check out its details view

[Screenshots Security Hub with S3 finding]

Now that you learned where to find notifications for security issues, let’s go ahead and fix the issue.

1. Use AWS Single Sign-On and access your AWS Workload Account
1. Open the [AWS S3 console](https://s3.console.aws.amazon.com/s3/home) again
1. Find your S3 bucket and click on its name to open the details view
1. Click on the “Properties” tab and find the “Default encryption” section
1. Click on the “Edit” button and enable the “Server-side encryption”
1. Save the changes

[Screenshots S3 settings]

To make sure that the problem is really fixed, you can go back to the [Security Hub console](https://eu-central-1.console.aws.amazon.com/securityhub/home?region=eu-central-1#/summary) and check that the finding no longer shows up.
