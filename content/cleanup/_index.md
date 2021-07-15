---
title: "Cleanup"
description: "Clean up data from the workshop."
chapter: true
weight: 70
---

# Clean up AWS resources

In this workshop, we created some resources in your account, if you no longer want to use these resources, you need to delete them. You can delete the resources using one of the options below:

1. Delete the stack instances using the AWS management console. Please follow steps below:
    1. Open the AWS management console and navigate to the AWS CloudFormation service.
    2. Select **Stacksets** from the left corner navigation plane. Choose the superwerker stack set.
    3. After selecting the superwerker stack, choose **Delete stacks from Stacksets** from the **Action** menu. See [this](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/stackinstances-delete.html#stackinstances-delete-console) link for more details.

2. If you have the AWS CLI installed, you can delete the stack using the AWS CLI command. See [this](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/stackinstances-delete.html#stackinstances-delete-cli) link for more details: `aws cloudformation delete-stack-instances --stack-set-name my-awsconfig-stackset --deployment-targets OrganizationalUnitIds='["ou-rcuk-1x5jlwo", "ou-rcuk-slr5lh0a"]' --regions '["eu-west-1"]' --no-retain-stacks`
