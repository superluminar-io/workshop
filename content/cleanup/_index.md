---
title: "Cleanup"
description: "The superwerker open source solution by AWS Advanced Partners kreuzwerker and superluminar automates the setup of an AWS Cloud environment with prescriptive best practices. It enables startups and SMBs to focus on their core business - by saving setup and maintenance time and money."
chapter: true
weight: 70
---

# Clean up AWS resources

In this workshop, we created some resources in your account, if you no longer want to use these resources, you need to delete them. You can follow the instructions below to remove your superwerker installation.

## Delete Subaccounts

Delete your subaccounts using the AWS management console:

WARNING: After performing these steps you will no longer have access to the AWS Account that you created for this workshop or the resources that they contain.

1. Navigate to AWS Organizations in the console of the AWS Root Aacount.
1. Click on 'List'

For each listed subaccount you need to perform the following actions:

1. Copy the email address under the subaccount name e.g. root+workload-exampleg@aws.example.com
1. Go to the AWS login page and use this copied email address to log in to the account.
1. You do not have an account password but that is not a problem, click "forgot password".
1. Fill in the captcha.
1. The password reset url has been sent to the AWS Systems Manager. So go back to your root account.
1. Navigate to the AWS Systems Manager and click on Parameter Store in the menu to the left.
1. Here you will find a parameter named [ETWAS], this is the password reset url you can use to change your password and log in to your account.
1. Reset your password using the password reset url.
1. Return to the login page and use the subaccount email address and newly reset password to log in to the subaccount your are trying to close.
1. Use the searchbar in the AWS console to navigate to AWS Billing
1. Scroll to the bottom of the page, in the small print there is a link to the account settings. Click this link.
1. Scroll to the bottom of the 'Account settings' page and click the red 'close account' button.

## Delete the Root User Account

- Log in as the Root user and perform steps 11-13 for your Root Account
