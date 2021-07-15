---
title: "Cleanup"
description: "Clean up data from the workshop."
chapter: true
weight: 70
---

# Clean up AWS resources

In this workshop, we created some resources in your account, if you no longer want to use these resources, you need to delete them. You can delete the resources using one of the below options:

- Delete the stack instances using AWS management console. Please follow below steps for the same:
    - Open the AWS management console and navigate to cloudformation service.
    - Select **Stacksets** from the left corner navigation plane. Choose the superwerker stack set.
    - After selecting superwerker stack, choose **Delete stacks from Stacksets** option from the **Action** menu. See [this](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/stackinstances-delete.html#stackinstances-delete-console) link for more details.
- If you have AWS CLI installed, delete the stack using the AWS CLI command. See [this](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/stackinstances-delete.html#stackinstances-delete-cli) link for more details: `aws cloudformation delete-stack --stack-name myteststack`