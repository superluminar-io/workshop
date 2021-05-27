---
title: "Secure Root Account"
chapter: true
weight: 1
---

# Single Sign-On

By now, you signed in to your AWS environment using the root users email address and password. This is considered a bad practices and [very insecure](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_root-user.html).

Therefore, the first step for securing your AWS environment is to configure the root user with multi-factor authentication and enable yourself to access your AWS Account using AWS Single Sign-On.

## MFA for the root user

The root user of an AWS Account has the broadest permissions possible. It is a huge security risk to leave this account only be secured with a single factor (a username and a password). To mitigate this risk, you need to enable multi-factor authentication for the root user. Start with logging into your AWS account.

![Sign In](/screenshots/sso/aws-signin.png)

Using the service selection or search field, access the AWS IAM service:

![IAM](/screenshots/sso/aws-iam.png)

The **IAM dashboard** of the **Identity and Access Management (IAM)** service shows a security alert for the root user.

![IAM Dashboard](/screenshots/sso/aws-iam-dashboard.png)

1. Click **Enable MFA** to access the [Security Credentials](https://console.aws.amazon.com/iam/home#/security_credentials$mfa) section of the IAM console
1. Click on the blue “Activate MFA” button
1. Select “Virtual MFA device”

![IAM](/screenshots/sso/aws-mfa-button.png)

![IAM](/screenshots/sso/aws-mfa-select.png)

1. Use a MFA application like [Google Authenticator](https://en.wikipedia.org/wiki/Google_Authenticator) or [Authy](https://authy.com/) to scan the QR code
1. Finish the setup by entering two consecutive MFA codes
1. Click the "Assign MFA” button

![IAM](/screenshots/sso/aws-mfa-assign.png)