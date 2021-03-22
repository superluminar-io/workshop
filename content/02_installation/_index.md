---
title: "superwerker Installation"
chapter: true
weight: 20
---

# superwerker installation

The installation of superwerker is a rather easy task. The only thing you have to do is launching a CloudFormation stack specific to the region you want superwerker to deploy to. Just click on the corresponding link in the superwerker installation manual (https://github.com/superwerker/superwerker#quick-install).

[Screenshot]

When you are logged into your AWS Account, you will be redirected to a prefilled CloudFormation stack configuration page where you can enable or disable different features of superwerker. For this workshop, we leave everything enabled which is the default setting.

[Screenshot of feature list?]

There is only one setting we must change at this point which is the “Domain for automated DNS configuration”. This determines the “domain used for root mail feature” and is necessary to do the basic multi account configuration via AWS Control Tower.

[Screenshot with filled domain input field]

Once you entered the domain, scroll down to the bottom of the page and acknowledge that CloudFormation might create IAM resources, such as Roles and Policies. To learn more about creating IAM Resources via CloudFormation see [Acknowledging IAM resources in AWS CloudFormation templates](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/using-iam-template.html#using-iam-capabilities).
Now start the superwerker installation by clicking on the “Create Stack” button.

You can now proceed with making the necessary DNS settings for your new superwerker installation.

## DNS Configuration

Superwerker is deployed through CloudFormation and uses multiple stacks to roll out its features. For the mandatory “root email feature” to work you need to bring a domain and do the related DNS settings accordingly. 

During the installation process, superwerker creates a Route53 hosted zone for domain and sub-domain you choose during “Domain configuration” earlier. Along with this hosted zone, Route53 creates a set of nameservers. Check the CloudFormation console to find out, if the “superwerker-Root-Mail” stack has been created.

[Screenshot of ready Cfn Stack]

Find the “next steps” link for your region in the [installation manual](https://github.com/superwerker/superwerker#quick-install). The link leads you to a CloudWatch dashboard that contains information on you superwerker setup. In the “DNS Settings” section you should find a list of Nameservers. Use these to set up a DNS delegation for your subdomain at your Domain hoster. If you choose to register a domain through Route53 you can find a [step-by-step guide here](https://docs.aws.amazon.com/Route53/latest/DeveloperGuide/dns-routing-traffic-for-subdomains.html#dns-routing-traffic-for-subdomains-new-hosted-zone).

## Finish superwerker setup

Once the DNS setting are done, the dashboard should reflect that by displaying a success message.

[Screenshot successful DNS setup]

Now you have to wait until the CloudFormation stacks are created successfully.

[Screenshot, all green CloudFormation Stacks]

Once this is done your superwerker setup is ready, and you can start configuring single sign-on via AWS Single Sign-On.
