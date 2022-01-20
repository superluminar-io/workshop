---
title: "Cleanup"
description: "The superwerker open source solution by AWS Advanced Partners kreuzwerker and superluminar automates the setup of an AWS Cloud environment with prescriptive best practices. It enables startups and SMBs to focus on their core business - by saving setup and maintenance time and money."
chapter: true
weight: 70
---

# Clean up AWS resources

In this workshop, we created some resources in your account, if you no longer want to use these resources, you need to delete them. You can delete the resources using one of the options below:

## Delete subaccounts

Delete your subaccounts using the AWS management console:

WARNING: After performing these steps you will no longer have access to the AWS Account that you created in this workshop or the resources that they contain.

1. Navigate to AWS Organizations in the console of the AWS Root Aacount.
2. Click on 'List'
3. For each listed subaccount copy the email address under the Account name e.g. root+workload-exampleg@aws.example.com
4. Now use this copied email address to login to the account.
5. You do not have an account password but that is not a problem, click "forgot password".
6. Fill in the captcha
7. Now go back to your root account.
8. Navigate to the AWS Systems Manager and click on Parameter Store in the menu to the left.
9. Here you will find a parameter named [ETWAS], this is the password reset url you can use to change your password and log in to your account.
10. Return to the login page and use your password to log in to the subaccount your are trying to close.
11. Use the searchbar in the AWS console to navigate to AWS Billing
12. Scroll to the bottom of the page, in the small print there is a link to the account settings. Click this link.
13. Scroll to the bottom of this page and click the red 'close account' button.

## Delete the Root User Account

- Log in as the Root user and perform steps 11-13 for your Root Account
