---
title: "Root-user Actions in Subaccounts"
description: "The superwerker open source solution by AWS Advanced Partners kreuzwerker and superluminar automates the setup of an AWS Cloud environment with prescriptive best practices. It enables startups and SMBs to focus on their core business - by saving setup and maintenance time and money."
chapter: true
weight: 20
---

# Perform Root-user Actions in Subaccounts

In some cases you will need to perform an action in a subaccount that can only be done by a root-user. For example. this is necessary if you want to change your support plan, enable multifactor authentication, or close the account. For a longer list of root-user actions see [this](https://docs.aws.amazon.com/general/latest/gr/root-vs-iam.html) documentation.

In this lab you will learn the steps you need to do to complete such actions.

## Signing into a Subaccount

First, navigate to your AWS Root Account.
Search for AWS Organizations in the search field at the top of the screen and select it when it appears.

![superwerker root-user-actions](/screenshots/perform-root-user-actions/navigate-to-organizations.png)

In AWS Organizations you will see your multi-account structure. Click on 'List'.

![superwerker root-user-actions](/screenshots/perform-root-user-actions/organization-structure.png)

Look for the account in which you want to perform a root user action and copy and paste the email address associated with the account.
Open an incognito window in your browser and navigate to the AWS login page. Paste the email address that you copied into the email field.

![superwerker root-user-actions](/screenshots/perform-root-user-actions/login-page.png)

You don't have a password right now because accounts created via organisations don't have a root user password. So click on "forgotten password".
Fill in the captcha.

![superwerker root-user-actions](/screenshots/perform-root-user-actions/password-recovery.png)

The password reset url has been sent to the AWS Systems Manager. So go back to your root account in the other window.
Navigate to the AWS Systems Manager and click on Parameter Store in the menu to the left.

![superwerker root-user-actions](/screenshots/perform-root-user-actions/navigate-to-systems-manager.png)

Here you will find a parameter that begins with "superwerker/rootmail/pw-reset-link/", this is where the password reset url is stored.
Click on the parameter and reset your password using the password reset url stored in the value field. Choose a strong password preferably with your preferred password manager.

![superwerker root-user-actions](/screenshots/perform-root-user-actions/password-reset-parameter.png)

Return to the login page in the incognito window and use the subaccount email address and newly reset password to log in to the account in which you wish to perform a root-user action.
From here on you can perform root-user actions for the subaccount that you are signed into.
