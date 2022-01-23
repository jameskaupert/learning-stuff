# Management and Developers Tools

## AWS Application Programming Interface (API)

Application Programming Interface (API) = software that allows two applications/services to talk to each other. Most commonly done via HTTP requests

The AWS API is an HTTP API that you can interact with by sending HTTP requests using an application like Postman

To authorize use you will need to generate a signed request. You authorize with your AWS credentials and get a token back

You will also have to provide an action and a payload

Generally, you will probably use other developer tools that use the AWS API rather than the AWS API directly, ie:

- AWS management console
- AWS SDK
- AWS CLI

The AWS General Reference at docs.aws.amazon.com contains details on interacting with AWS services via the API

## AWS Management Console

AWS Management Console = web-based unified console to build, manage, and monitor everything created on AWS

console.aws.amazon.com

ClickOps = Point-and-click to manually launch and configure AWS resources with limited programming knowledge.

## AWS Account ID

Every AWS account has a unique account ID. This can be found in the user profile in the global navigation at the top right of the console

Used for

- logging in with a non-root user account
- cross-account roles
- support cases

Generally good to keep the account ID private as malicious actors need it to perform an attack on the account

## AWS Tools for PowerShell

Powershell = is a task automation and configuration management framework. Both a command-line shell and a scripting language

Unlike most shells, which accept and return text, PowerShell is built on top of the .NET Common Language Runtime (CLR) and accepts and returns .NET objects

AWS Tools for PowerShell lets you interact with the AWS API via PowerShell Cmdlets (special types of commands in PowerShell with capitalized verb-and-noun, ie: New-S3Bucket)

Can set AWS Cloud Shell to use PowerShell by typing `pwsh` at the prompt

## Amazon Resource Names

Amazon Resource Names (ARNs) uniquely identify resources unambiguously across all of AWS

Formats:

- arn:partition:service:region:account-id:resource-id
- arn:partition:service:region:account-id:resource-type/resource-id
- arn:partition:service:region:account-id:resource-type:resource-id

Partitions:

- aws (Global AWS)
- aws-cn (China regions)
- aws-us-gov (US GovCloud)

For resources that are global like S3, it may look like `arn:aws:s3:::my-bucket`, omitting unnecessary details

Can include wildcard characters to specify groups of ARNs

## AWS Command Line Interface (CLI)

Command Line Interface (CLI) = a tool to process commands to a computer program in the form of lines of text

Operating systems implement a CLI in a shell

Terminal = text-only interface for input/output

Console = physical computer to physically input information into a terminal

Shell = the command line program that users interact with to input commands
Popular shell programs:

- Bash
- Zsh
- PowerShell

AWS CLI allows users to programmatically interact with the AWS API via entering single or multi-line commands into a shell/terminal

Can use the AWS CLI via the CloudShell (only in some regions). Credentials are already set up for the account you are in

## AWS SDK

Software Development Kit (SDK) = collection of software development tools in one installable package

You can use the AWS SDK to programmatically create, modify, delete, or interact with AWS resources

- AWS SDK is offered in many programming languages

## AWS CloudShell

- browser-based shell built into the AWS console. Scoped per-region, with the same credentials as the logged-in user, and is free
- includes some pre-installed Linux tools, the AWS CLI, Python, Node, etc...

## Infrastructure as Code (IaC)

You write a configuration script to automate creating, updating, or destroying cloud infrastructure

- IaC is a blueprint of your infrastructure
- IaC allows you to easily share, version, and inventory your cloud infrastructure

Two versions of writing IaC in AWS:

1. Cloudformation (CFN) - declarative
2. Cloud Development Kit (CDK) - imperative

Declarative

- what you see is what you get (Explicit)
- more verbose, but zero chance of misconfiguration
- uses scripting languages (JSON, YAML, XML)

Imperative

- you say what you want and the rest is filled in (Implicit)
- less verbose, but you could end up with misconfiguration
- does more than Declarative can
- uses programming languages (Python, TypeScript, etc...)

### CloudFormation

- can write IaC as either JSON or YAML (more typically)
- CloudFormation is simple, but can lead to large files and can be limited in some regard when creating dynamic or repeatable infrastructure
- CloudFormation can be easier for DevOps engineers who do not have a background in web programming languages
- Since the CDK generates CloudFormation, it is still important to understand CloudFormation for debugging

### CDK

- can write IaC using various programming languages
- powered by CloudFormation (generates Cloudformation templates)
- has large library of reusable cloud components at https://constructs.dev
- comes with its own CLI
- CDK Pipelines allows quick setup of CI/CD pipelines for CDK projects
- CDK has a testing framework for Unit/Integration testing
- CDK and SDK look similar, but the CDK creates idempotent infrastructure instead of continually creating new things every time code is rerun

## AWS Toolkit for VSCode

- open-source plugin for VSCode to create, debug, and deploy AWS resources

Includes:

1. AWS Explorer - explore a wide range of AWS resources linked to your AWS account
2. AWS CDK Explorer - explore stacks defined by CDK
3. AWS Elastic Container Service - provides intellisense for ECS task definition files
4. Serverless Applications - create, debug, and deploy serverless applications via SAM and CFN

## Access Keys

Access Key = key and secret (credentials) required to have programmatic access to AWS resources via the AWS API outside of the console

- A user must be granted access to use access keys
- never share access keys
- never commit access keys to a codebase
- can have 2 active access keys
- can deactivate access keys
- access keys have whatever access a user would have

## AWS Documentation

Large collection of technical documentation on how to use AWS services

https://docs.aws.amazon.com
