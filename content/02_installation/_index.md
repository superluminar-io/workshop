---
title: "superwerker Installation"
chapter: true
weight: 20
alias: why
---

# superwerker setup

## Installing superwerker

Getting started with [superwerker] is simple: You only need to deploy a single AWS CloudFormation template into an existing AWS account. Head over to the [superwerker repository on GitHub], choose the [GitHub releases], and pick the most recent version to get started.

## AWS CloudFormation

After clicking on the **Quick Install** link on GitHub, you will be redirected to the AWS Management Console to deploy the CloudFormation template for [superwerker].

[Screenshot]

If you are not already signed in to your AWS Account, you will be asked for your login information.

> In general, the CloudFormation template for superwerker supports disabling of optional components for superwerker; for this workshop, please keep all services enabled.

The only important configurations for this workshop are the domain name and sub domain. For a fundamental feature of superwerker, called **RootMail**, you need to have a dedicated domain you can use with superwerker.

If your company's primary domain is `example.com` you can consider a domain like `aws.example.com` for using with superwerker. The DNS configuration is split up into two input fields: one for the domain, and one for the intended sub domain.

[Screenshot of feature list?]

**Warning:** Please ensure you have access to the DNS configuration of your configured domain! Without the needed settings, you cannot continue this workshop and the installation of superwerker!

[Screenshot with filled domain input field]

Once you entered the domain information, scroll down to the bottom of the page and acknowledge that AWS CloudFormation needs to create IAM resources; such as Roles and Policies.

> To learn more about creating IAM Resources via CloudFormation see [Acknowledging IAM resources in AWS CloudFormation templates](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/using-iam-template.html#using-iam-capabilities).

With clicking **Create Stack**, you can now start the installation!

## DNS Configuration

During the installation process, [superwerker] creates a **Route53 hosted zone** for the domain and sub-domain you configured prior starting the installation. Along with this hosted zone, Route53 creates a set of nameservers the be used for your domain.

[superwerker] uses **Nested CloudFormation Stacks** to organize and bundle the included components. To figure out, if the needed Route53 resources have been created, check the status of the `superwerker-Root-Mail` stack in AWS CloudFormation.

[Screenshot of ready Cfn Stack]

When the CloudFormation stack was created, head over to AWS CloudWatch and access the section for dashboards. [superwerker] will create a custom dashboard to maintain a [living documentation] for installation instructions, next steps, and standard operating procedures

[Screenshot of CloudWatch]

At the “DNS Settings” section, you will find a list of nameservers. Use these servers to set up a DNS delegation for your sub domain.

> If you choose to register a domain through Route53 you can use the [step-by-step guide from AWS](https://docs.aws.amazon.com/Route53/latest/DeveloperGuide/dns-routing-traffic-for-subdomains.html#dns-routing-traffic-for-subdomains-new-hosted-zone).

The installation process of [superwerker] waits until you have finished setting up the DNS configuration. There is no need to confirm the changes, the AWS CloudFormation template will periodically check for the needed configuration and continue automatically afterwards.

## Finish superwerker setup

After the installation process recognized the needed DNS configuration, the dashboard in AWS CloudWatch will reflect the correct nameservers for your domain.

[Screenshot successful DNS setup]

Together with updating the dashboard, [superwerker] will continue with creating the additional resources now. The events for the stack in AWS CloudFormation show you the installation progress.

[Screenshot in-progress CFN stack]

While the remaining resources get created, you can head over to the next steps in this workshop:

- [Why do you need a multi-account AWS environment?](/03_why.html)
- [What costs occur after installing superwerker?](/04_costs.html)

Make sure to head back at CloudFormation regularly, to check if the [superweker] stack has been created successfully.

[superwerker repository on github]: https://github.com/superwerker/superwerker
[github releases]: https://github.com/superwerker/superwerker/releases
[superwerker]: https://superwerker.cloud
[living documentation]: https://console.aws.amazon.com/cloudwatch/home#dashboards:name=superwerker
