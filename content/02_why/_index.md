---
title: "The Why"
chapter: true
weight: 23
---

# Why do I need all this?

## Do we really need superwerker from the beginning?

Most organizations start small on AWS. Usually, there is a bit of prototyping or a single application should be migrated. There are not many moving parts involved and everything is happening in a single AWS account.

So, why do we recommend a multi account setup even for such small environments? The simple answer is: They will grow big. And when they do, it’s very hard to adjust everything to use a multi account strategy. 

## But why do we need it in the first place?

There are many good reasons to have a multi account setup with AWS. The most important one are:

- **Blast radius reduction**. If something bad happens, it usually affects only one account.
- **Cost attribution**. The simplest way to split AWS spendings is by distributing workloads over multiple accounts.
- **Least privilege made easy**. AWS accounts are a privilege boundary in AWS, and it’s easy to limit the access e.g. for a team to their account.
- **Support innovation**. It is easy for developers to try out new features if they have their “playground” account and know they can’t interfere with production workloads.

## Further reads

There are a good deal of information on this topic. Here is a small list, if you want to know more:

- [The reasons why you want an AWS multi-account strategy](https://kreuzwerker.de/post/AWS-multi-account-strategies)
- [Advantages of AWS Multi-Account Architecture](https://ruempler.eu/2017/07/09/advantages-aws-multi-account-architecture/)
- [Establishing your best practice AWS environment](https://aws.amazon.com/organizations/getting-started/best-practices/)
