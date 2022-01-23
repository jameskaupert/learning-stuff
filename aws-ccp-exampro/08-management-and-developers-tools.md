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
