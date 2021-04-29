---
title: "Secure a simple workload"
chapter: true
weight: 30
---

# Secure a simple workload

In this lab we are going to create a first basic AWS resource, an S3 bucket. It could for instance be used to store some internal file or as an asset backend for a static website.
While doing this we will make some intentional mistakes to showcase some of the security feature that was enabled by superwerker for you.
As a workload owner, we want to get notified, when we made an insecure configuration of an AWS resource accidentally.

## Create the S3 bucket

The creation of an S3 bucket is straightforward via the AWS S3 console:

1. Open the [AWS S3 console](https://s3.console.aws.amazon.com/s3/home)
1. Click the orange “Create bucket” button
1. Choose a name and a region for the bucket. Keep in mind that the bucket name needs to be unique over all buckets (not just in your AWS account)
1. Keep the default settings for everything else. Especially: **do not** enable “Server-side encryption”.
1. Finish the bucket creation by clicking the “Create bucket” button

[Screenshots of bucket create form]

Now we have a newly created bucket without server-side encryption. Let’s see if there are security warnings, that can help us to mitigate this risk.

## Security Notification via Security Hub

Now we need to check if our misconfiguration (unencrypted bucket) got already noticed. There are two services involved in this process:

- AWS Config check continuously all AWS resource against a set of rules
- AWS Security Hub aggregate all security related notifications in a clearly arranged dashboard

To check the current security issues in our workload account, we need to perform the following steps:

1. Open the [Security Hub console](https://eu-central-1.console.aws.amazon.com/securityhub/home?region=eu-central-1#/summary)
1. Select “Findings” from the navigation bar
1. Locate the finding related to the new S3 bucket in the list (it might take a couple of minutes until it appears)
1. You can take a closer look at the finding and check out its details view
[Screenshots Security Hub with S3 finding]

Now that we learned where to find notifications for security issues, let’s go ahead and fix the it.

1. Open the [AWS S3 console](https://s3.console.aws.amazon.com/s3/home) again
1. Find the newly create bucket and click on its name to open the details view
1. Click on the “Properties” tab and find the “Default encryption” section
1. Click on the “Edit” button and enable the “Server-side encryption”
1. Save the changes

[Screenshots S3 settings]

To make sure that the problem is really fixed, we go back to the [Security Hub console](https://eu-central-1.console.aws.amazon.com/securityhub/home?region=eu-central-1#/summary) again and check that the finding no longer shows up.
