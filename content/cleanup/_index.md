---
title: "Cleanup"
description: "The superwerker open source solution by AWS Advanced Partners kreuzwerker and superluminar automates the setup of an AWS Cloud environment with prescriptive best practices. It enables startups and SMBs to focus on their core business - by saving setup and maintenance time and money."
chapter: true
weight: 70
---

# Clean up AWS resources

In this workshop, we created some resources in your account, if you no longer want to use these resources, you need to delete them.

Closing accounts is an example of a root-user action. So you need to sign into each of your subaccounts using the steps described in the lab: "Performing root-user actions" and then close them using the instructions below.

## Delete Subaccounts

WARNING: After performing these steps you will no longer have access to the AWS Account that you created for this workshop or the resources that they contain.

After following the steps in the "Performing root-user actions" lab to sign into one of your subaccounts...

1.  Use the subaccount email address and your newly reset password to log in to the subaccount you are trying to close.

    ![superwerker cleanup](/screenshots/cleanup/cleanup-login-to-subaccount.png)

1.  Click on your account name in the top right corner of the console.
1.  Select Account

    ![superwerker cleanup](/screenshots/cleanup/cleanup-go-to-account-settings.png)

1.  Scroll to the bottom of the 'Account' page
1.  Tick all the boxes to agree to close your subaccount
1.  Click the red 'close account' button.

    ![superwerker cleanup](/screenshots/cleanup/cleanup-close-account-button.png)

1.  Repeat these steps for each of your subaccounts until only your root account remains.
1.  Now use the same procedure to delete your root user account.
