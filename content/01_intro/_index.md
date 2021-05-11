---
title: "Introduction"
chapter: true
weight: 10
---

# Introduction

## Goal Of The Workshop

After finishing this workshop, you know everything about the foundational concepts to manage a multi-account AWS environment.

You will start with installing [superwerker]; an official [AWS Quick Start] solotion and automated gold-standard deployment in the AWS Cloud. Based on best practices and experiences from years of consulting, [superluminar] and [kreuzwerker] created the [superwerker] open-source solution.

## High-Level Overview

Getting started with [superwerker] is simple: You only need to deploy a single AWS CloudFormation template into an existing AWS account. Afterwards, the main goal of the workshop is to teach you how to facilitate superwerker for maintaining a secure and sustainable AWS environment in a best practice-driven fashion.

When the installation process is done, this workshop will guide you through the decisions and service configurations [superwerker] implies for you and you will learn why they are in place.

Additionally, uou will walk through some typical scenarios when it comes to maintaining larger AWS environments like:

- Managing Users and Access
- Restore automatically created backups
- Aggregate, organize, and prioritize security alerts
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
