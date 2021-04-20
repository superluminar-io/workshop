---
title: "AWS Organization"
chapter: true
weight: 20
---

# AWS Organization Structure

When using AWS Organizations, AWS Accounts are organized organizational units (OUs). This allows to manage groups of accounts as one unit and therefore simplifies it by a lot. During it’s set up AWS Control Tower already created two OUs for us: “core” and “custom”.

In this lab we are going to create a first organizational unit. We will later use this to create a first workload account. We could just use the “custom” OU but for educational purposes we will be creating a new one.

## Create an OU

All operations concerning AWS Organizations must be made from the organizations root account. To create a new OU we have to do the following steps:

1. Log into the organizations root account
1. Go to the [Control Tower Management Console](https://eu-central-1.console.aws.amazon.com/controltower/home/dashboard?region=eu-central-1)
1. Click on "Organizational units" in navigation bar
1. Click on the "Add an OU" button
1. Choose a name for the OU (e.g. Workloads_Test) and create it by clicking the "Add" button

[Screenshots]

Now that we have a dedicated OU, we can create our first workload account.

## Create a workload account

We want to separate our core accounts from the workload accounts. Therefore, we are going to create a dedicated workload account in the newly created OU. 

Since we want to establish a well-maintained baseline throughout all of our workload accounts, we are going to use the Control Tower Console to create a new account. This will not only create a new AWS account for us, but will also roll out all configured guardrails to this new account.

To create a new account, we need to perform the following steps:

1. Log into the organizations root account
1. Go to the [Control Tower Management Console](https://eu-central-1.console.aws.amazon.com/controltower/home/dashboard?region=eu-central-1)
1. Select “Account factory” from the navigation bar
1. Click on “Enroll account”
1. Fill in the details and make sure to use the new OU
1. Click on “Enroll account” to start the account creation process

[Screenshots account creation]

It can take some time until the new account is ready. You can check the status on the “Accounts” overview of the Control Tower console.
