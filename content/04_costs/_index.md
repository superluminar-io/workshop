---
title: "Cost"
chapter: true
weight: 40
---

# Costs of a superwerker setup

The installation and usage of [superwerker] is free of charge! The project and all included components is are available as open-source and provided using the [MIT licence](https://github.com/superwerker/superwerker/blob/main/LICENSE.md).

> Of course, costs will be incurred by the AWS services [superwerker] sets up. For a smaller environments, the monthlys costs will be less than $10.

## Included Services

The goal of [superwerker] is to provide you with a set of well-configured AWS services. These services come with their default pricing depending on the AWS region you use:

- [AWS Security Hub](https://aws.amazon.com/security-hub/pricing/)
- [Amazon Route 53](https://aws.amazon.com/route53/pricing/)
- [AWS Config](https://aws.amazon.com/config/pricing/)
- [Amazon S3](https://aws.amazon.com/s3/pricing/)
- [Amazon GuardDuty](https://aws.amazon.com/guardduty/pricing/)
- [AWS Systems Manager](https://aws.amazon.com/systems-manager/pricing/)

> As a rule of thumb: The costs for these services will grow with the number of AWS accounts and the number of workloads (EC2 instances, databases, Lambda functions, …) you use.

Given the benefits of a multi-account AWS environment, this is a justifiable invest.

[superwerker]: https://github.com/superwerker/superwerker
