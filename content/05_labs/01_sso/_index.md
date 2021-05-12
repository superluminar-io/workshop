---
title: "Single Sign-On"
chapter: true
weight: 10
---

# Single Sign-On

By now, you signed in to your AWS environment using the root users email address and password. This is considered a bad practices and [very insecure](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_root-user.html).

Therefore, the first step for securing your AWS environment is to configure the root user with multi-factor authentication and enable yourself to access your AWS Account using AWS Single Sign-On.

## MFA for the root user

The root user of an AWS Account has the broadest permissions possible. It is a huge security risk to leave this account only be secured with a single factor (a username and a password). To mitigate this risk, you need to enable multi-factor authentication for the root user with the following steps:

1. Log in to your AWS Account with your root user's email address and password
1. Access the [Security Credentials](https://console.aws.amazon.com/iam/home#/security_credentials$mfa) section of the IAM console
1. Click on the blue “Activate MFA” button
1. Select “Virtual MFA device”
1. Use a MFA application like [Google Authenticator](https://en.wikipedia.org/wiki/Google_Authenticator) or [Authy](https://authy.com/) to scan the QR code
1. Finish the setup by entering two consecutive MFA codes
1. Click the “activate MFA” button

[Screenshots of the process]

## AWS Single Sign-On

After securing your root account, it is time to enable login via AWS Single Sign-On.

### Basics

The AWS Single Sign-On service allows you to create new user accounts that only exist in AWS SSO as well as connecting it to an existing identity provider like Googles G Suite or Azure AD.

> To keep the workshop simple, we reference the AWS documentation on [how to use G Suite as an external identity provider for AWS SSO](https://aws.amazon.com/blogs/security/how-to-use-g-suite-as-external-identity-provider-aws-sso/) as well as the generic documentation on [how to manage your identity source with AWS SSO](https://docs.aws.amazon.com/singlesignon/latest/userguide/manage-your-identity-source.html) here.

### Enable your admin account

Since you learned that you should not use your root account to do day-to-day tasks, you need a new account that satisfies this requirement. Luckily, AWS Control Tower integrates with AWS Single Sign-On and has already created an administrator account during the setup phase for you. You have received an email with an activation link for this exact account.

To enable the user account, accept the invitation:

1. Open the email with the subject “Invitation to join AWS Single Sign-On”
1. Read through the content
1. Click on the “Accept Invitation” link
1. Choose a new password and store it along with the username in a secure location

You can also see the URL of your AWS Single Sign-On login. Per default, it is a random sub domain, but you will be able to customize it in the next steps.

[Screenshots of the process]

Together with the URL of your AWS Single Sign-On service and the new user account, you can access your AWS account without the need of the root user account.

### Custom Login URL

To make the usage of AWS Single Sign-On more convenient, AWS supports changing the custom sub domain for the login page.

> The AWS Single Sign-On service is - as most AWS services - bound to a specific AWS region for a specific AWS account. To manage settings regarding your new login process, you need to access the Single Sign-On service in the AWS account and region you used to create the [superwerker] CloudFormation stack.

There are two important things to be aware of when changing the user portal URL:

- This is a public domain, so it needs to be unique over all AWS customers
- You can only change this URL once!

![CloudFormation for superwerker](/screenshots/sso/custom-domain.png)

To change the sub domain, perform these steps:

1. Log in to the AWS Root Account
1. Access the AWS Single Sign-On service
1. Go to the “Settings” section
1. Click to button to customize the “User portal URL”
1. Enter a customized sub domain

[superwerker]: https://github.com/superwerker/superwerker
