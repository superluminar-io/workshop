---
title: "Single Sign-On"
chapter: true
weight: 10
---

# Single Sign-On

By now you should only be able to log into your AWS environment using the root users email address and password. This is considered a bad practices and [very insecure](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_root-user.html).

Therefore, the next step for you is to secure the root user with multi-factor authentication and enable yourself to securely log into your AWS Account using AWS Single Sign-On.

## Multi-Factor Authentication for the root user

The root user of an AWS Account has the broadest permissions possible. Therefore, it is a huge security risk to let this account be only secured with a single factor (a username and a password). To mitigate this risk, you are going to enable multi-factor authentication for this user account with the following steps:

1. Log into your AWS Account with your root users email address and password
1. Go to the [Security Credentials](https://console.aws.amazon.com/iam/home#/security_credentials$mfa) section of the IAM console
1. Click on the blue “Activate MFA” button
1. Select “Virtual MFA device”
1. Use your favourite MFA app like Google Authenticator, Authy or whatever you prefer to scan the QR code
1. Finish the setup by entering two consecutive MFA codes click the “activate MFA” button

[Screenshots of the process]

## AWS Single Sign-On

### Basics

Now that you secured your root account, it is time to enable login via AWS Single Sign-On. This service allows you to create new user accounts that only exist in AWS SSO as well as connecting it to an existing identity provider like Googles G Suite or Azure AD.
To keep the workshop simple, we reference the AWS documentation on [how to use G Suite as an external identity provider for AWS SSO](https://aws.amazon.com/blogs/security/how-to-use-g-suite-as-external-identity-provider-aws-sso/) as well as the generic documentation on [how to manage your identity source with AWS SSO](https://docs.aws.amazon.com/singlesignon/latest/userguide/manage-your-identity-source.html) here.

### Enable your admin account

Since you learned that you should not use your root account to do your day-to-day tasks, you need a new account that satisfies this requirement. Luckily, AWS Control Tower integrates with AWS SSO and create an administrator account during the setup phase for you. You should have received an email with an activation link for this exact account.

To enable this new account do the following:

1. Open the email with the subject “Invitation to join AWS Single Sign-On”
1. Read through the content
1. Click on the “Accept Invitation” link
1. Choose a new password and store it along with the username in a secure location

You can also learn the sub-domain your AWS SSO login is available from the invitation email. It is a random string, and you will be going to change it in one of the next steps.

[Screenshots of the process]

### Change the AWS SSO login sub-domain

AWS SSO is a service that manages access on an organizational level (as opposed to per account-level). Therefore, it needs to be configured in a central location. For AWS SSO this is the root account.

There are two things to be aware of when changing the user portal URL:

- This is a public domain, so it needs to be unique over all AWS customers
- You can only change this URL once!

To change the login sub-domain, perform the following steps:

1. Log into the Root AWS Account
1. Open the AWS SSO Console
1. Go to the “Settings” section
1. Find the “User portal URL” and click on customize
1. Enter a sub-domain

[Screenshots of the process]
