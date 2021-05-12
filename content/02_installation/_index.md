---
title: "superwerker Installation"
chapter: true
weight: 20
alias: why
---

# superwerker setup

## Installation Prerequisites

To install [superwerker], you need to fulfil the following two prerequisites:

1. A dedicated AWS Account with administrative access ([sign up here](https://portal.aws.amazon.com/billing/signup))
1. A domain and manageable DNS settings (You can register domains with [Amazon Route53](https://docs.aws.amazon.com/Route53/latest/DeveloperGuide/domain-register.html))

if these are in place, you can now begin the installation process.

## Installing superwerker

Getting started with [superwerker] is simple: You only need to deploy a single AWS CloudFormation template into an existing AWS account.

1. Sign into your AWS account if you are not already logged in.
1. Check in the upper-right corner of the AWS console that you are in the region in which you want to deploy superwerker.
1. Click on this ([github releases](https://github.com/superwerker/superwerker/releases)) link, then select **Quick install** for the latest version of [superwerker].

![GitHub releases for superwerker](/screenshots/installation/github-releases.png)

After clicking on the **Quick Install** link on GitHub, you will be redirected to the AWS Management Console to deploy the CloudFormation template for [superwerker].

![CloudFormation for superwerker](/screenshots/installation/cloudformation-start.png)

## AWS CloudFormation

The CloudFormation template for superwerker supports disabling of optional components for superwerker but for this workshop, please keep all services enabled.

![CloudFormation for superwerker](/screenshots/installation/domain-empty.png)

The only important configurations for this workshop are the domain name and sub domain. For a fundamental feature of superwerker, called **RootMail**, you need to have a dedicated domain you can use with superwerker.

If your company's primary domain is `example.com` you can consider a domain like `aws.example.com` to use with superwerker. The DNS configuration is split up into two input fields: one for the domain, and one for the intended sub domain.
> **Warning:** Please ensure you have access to the DNS configuration of your configured domain! Without the needed settings, you cannot continue this workshop and the installation of superwerker!

1. Fill in the Domain for automated DNS configuration (see the screenshot below)
1. Scroll down to the bottom of the page and tick the boxes acknowledging that CloudFormation might create IAM resources such as Roles and Policies
1. Click the **Create Stack** button and it will start the installation!

![CloudFormation for superwerker](/screenshots/installation/domain-filled.png)

> Further reading:
>
> creating IAM Resources via CloudFormation see [Acknowledging IAM resources in AWS CloudFormation templates](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/using-iam-template.html#using-iam-capabilities).

## DNS Configuration

During the installation process, [superwerker] creates a **Route53 hosted zone** for the domain and sub-domain you configured prior starting the installation. Along with this hosted zone, Route53 creates a set of nameservers to be used for your domain.
[superwerker] uses **Nested CloudFormation Stacks** to organize and bundle the included components. You need to figure out, if the needed Route53 resources have been created.

1. Check the status of the `superwerker-Root-Mail` stack in AWS CloudFormation, when it is ready, it should look like the screenshot below (you may have to wait a couple of minutes).

[Screenshot of ready Cfn Stack]

2. If the stack is ready, use the search bar in the console to go to AWS cloudwatch.

[Screenshot of CloudWatch]

3. On the menu on the left side of the Cloudwatch console, click 'Dashboards'. 
4. You will find that superwerker has created a custom dashboard for you, named superwerker. Click on the link to this dashboard.

The [superwerker] dashboard maintains a [living documentation] for installation instructions, next steps, and standard operating procedures

5. In the “DNS Settings” section, you will find a list of nameservers. Use these servers to set up a DNS delegation for your sub domain.

The installation process of [superwerker] waits until you have finished setting up the DNS configuration. There is no need to confirm the changes, the AWS CloudFormation template will periodically check for the needed configuration and continue automatically afterwards.

> note: If you choose to register a domain through Route53 you can use the [step-by-step guide from AWS](https://docs.aws.amazon.com/Route53/latest/DeveloperGuide/dns-routing-traffic-for-subdomains.html#dns-routing-traffic-for-subdomains-new-hosted-zone).

## Finish superwerker setup

After the installation process recognized the needed DNS configuration, the dashboard in AWS CloudWatch will reflect the correct nameservers for your domain.

![CloudFormation for superwerker](/screenshots/installation/dashboard-done.png)

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
