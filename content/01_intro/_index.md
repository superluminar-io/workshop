---
title: "Introduction"
chapter: true
weight: 10
---

# Introduction

## Goal Of The Workshop

After finishing this workshop, you will understand the fundamental concepts that are required to set up and maintain a secure multi-account AWS environment.

You will install [superwerker]; an official [AWS Quick Start] solution that automates the deployment of AWS services in the cloud. Superwerker has been developed by [superluminar] and [kreuzwerker] to follow best practices for security and efficiency based on their decades of experience as cloud computing consultants.

## Workshop overview

In this workshop you will install and deploy superwerker via AWS CloudFormation into an existing AWS account. We will then guide you through the decisions and service configurations that [superwerker] performs for you and you will learn why they are in place.

You will also get to experience some typical scenarios related to maintaining larger AWS environments like:

- Managing Users and Access
- Restoring automatically created backups
- Aggregating, organizing, and prioritizing security alerts
- Onboarding existing AWS Accounts in your new AWS Environment

## AWS Environments

Multi-account environments enable improved security and cost outcomes. They contribute to key metrics like development and deployment velocity by retaining the technological freedom for small and independent workload teams. Managing a cloud infrastructure consisting of multiple AWS accounts is therefore one of the most important but also complex topics for Well-Architected AWS environments.

## Prerequisites

To install [superwerker], you need to fulfil the following two prerequisites:

1. A dedicated AWS Account with administrative access ([sign up here](https://portal.aws.amazon.com/billing/signup))
2. A domain and manageable DNS settings (You can register domains with [Amazon Route53](https://docs.aws.amazon.com/Route53/latest/DeveloperGuide/domain-register.html))

When you have these in place, you can beginn with [installing superwerker].

[superwerker]: https://github.com/superwerker/superwerker
[aws quick start]: https://aws.amazon.com/quickstart/architecture/superwerker/
[superluminar]: https://superluminar.io
[kreuzwerker]: https://kreuzwerker.de
[installing superwerker]: /02_installation.html
