# Governance

## Organizations and Accounts

AWS Organizations = allows creation of new AWS accounts. Centrally manage billing, control access, compliance, security, and share resources across your AWS accounts

Root Account User = the only sign in identity that has complete access to all AWS services and resources in an account. Each account has a Root Account User

Organizational Units = group of AWS accounts within an organization which can also contain other organizational units, creating a hierarchy

Service Control Policies = gives central control over allowed permissions for all accounts in your organization, helping to ensure your accounts stay within your organization's guidelines (IAM policies defined for an entire organization or account(s))

AWS Organizations must be turned on, and cannot be turned off once on

You can create as many AWS Accounts as you like - one will be the Master/Root account

## AWS Control Tower

AWS Control Tower = helps enterprises quickly set up a secure, AWS multi-account environment. Provides a baseline environment to get started with multi-account architecture

Landing Zone = baseline envrionment following well-architected and best practices to start launching production-ready workloads

- AWS SSO enabled
- centralized logging for AWS CloudTrail
- cross-account security auditing

Account Factory

- automates provisioning of new accounts in your organization
- standardizes the provisioning of new accounts with pre-approved account configs
- configure your account factory with pre-approved network configuration and region selections
- enable self-service for your builders to configure and provision new accounts using AWS Service Catalog

Guardrails

- pre-packaged governance rules for security, operations, and compliance that customers can select and apply enterprise-wide or to specific groups of accounts
- replacement for the now-retired AWS Landing Zones

## AWS Config

Change Management = formal process to monitor, enforce, and remediate changes

Compliance as Code (CaC) = utilizing programming to automate the monitoring, enforcing, and remediation of changes to stay compliant with compliance programs or expected configuration

AWS Config = compliance-as-code framework that allows changes to be managed in AWS accounts on a per region basis. Used for:

- resources that need to stay configured a specific way for compliance
- keeping track of configuration changes to resources
- listing all resources within a region
- analyzing potential security weaknesses and you need detailed historical info

## AWS Quick Starts

AWS Quick Starts are prebuilt templates by AWS and AWS Partners to help deploy a wide range of stacks

Composed of 3 parts:

1. reference architecture for the deployment
2. AWS Cloudformation templates that automate and configure the deployment
3. A deployment guide explaining the architecture and implementation in detail

## Tagging

Tag = key and value pair you can assign to AWS resources to allow you to organize resources

- resource management
- cost management/optimization (cost tracking / budgets / alerts)
- operations management (business commitments and SLA operations)
- security (classification of data/security impact)
- governance and regulatory compliance
- automation
- workload compliance

Can be used with IAM policies to restrict access

## Resource Groups

Resource Groups = collection of resources that share one or more tags

- helps organize and consolidate information based on project and resources you use
- can display details about a group of resources based on
  - metrics
  - alarms
  - config settings

You can change the settings of your groups at any time to change what resources appear

## Business Centric Services

Amazon Connect = virtual call center service. Create workflow to route callers. Can record phone calls, manage a queue of callers.

WorkSpaces = virtual remote desktop service. Secure managed service for provisioning Windows or Linux desktops

WorkDocs = shared collaboration service. Centralized storage to share content and files. Similar to SharePoint

Chime = video conference service, similar to Zoom or Skype. Can screenshare, have multiple people on the call. Secure by default and can show a calendar of upcoming calls

WorkMail = managed business email, contacts, and calendar service. Similar to Gmail or Exchange

Pinpoint = marketing campaign management service. Used for sending targeted email via SMS, push notifications, and voice messages. Perform A/B testing or create Journeys (complex email response workflows)

Simple Email Service (SES) = transactional email service. Integrate into application to send emails. Create common templates, track open-rates, keep track of reputation

QuickSight = Business Intelligence (BI) service. Connect multiple data sources and quickly visualize data in the form of graphs with minimal programming knowledge
