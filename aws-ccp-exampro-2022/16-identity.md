# Identity

## Zero-Trust Model

> "Trust no one, verify everything."

Bad actors have proven that conventional access-controls can be bypassed such that traditional security measures are insufficient

Identity is the primary security perimeter in the Zero Trust model

Primary Security Perimeter = first line of defense to protect company resources and assets

Network-Centric (old way) = traditional security model focusing on firewalls and VPNs since few employees/workstations were outside the office, or they were in specific remote offices

Identity-Centric (new way) = bring-your-own-device, remote workstations are becoming much more common. Cannot trust if employee is in secure location. Identity-based security controls like MFA, or providing provisional access based on level of risk from where/when/what user wants to access

- does not replace, but augments network-centric security

## Zero-Trust on AWS

Identity Security Controls on AWS:

- Identity and Access Management
  - IAM policies
  - Permission Boundaries
  - Service Control Policies (organization-wide)
  - IAM Policy Conditions
    - aws:SourceIp = restrict on IP address
    - aws:RequestedRegion = restrict on region
    - aws:MultiFactorAuthPresent = restrict on MFA missing
    - aws:CurrentTime = restrict on time of day

AWS does not have ready-to-use identity controls, which is why AWS is considered not to have a true Zero Trust offering and third party services need to be used

Services that can be used to set up intelligent-ish detection of identity concerns, but requiring expert knowledge

- AWS CloudTrail = track all API calls
- Amazon GuardDuty = detects suspicious or malicious activity based on CloudTrail and other logs
- Amazon Detective = used to analyze, investigate and quickly identify security issues (can ingest from GuardDuty)

Azure AD has real-time and calculated risk detection based on more data points than AWS, with more robust security controls, verifications, or logic restriction

Other 3rd party identity solutions

- Azure AD
- Google BeyondCorp
- JumpCloud

Connect 3rd party solutions through AWS SSO for more robust functionality

## Directory Service

Directory Service = maps the names of network resources to their network addresses

Directory service is shared information infrastructure for locating, managing, administering, and organizing resources:

- volumes
- folders
- files
- printers
- users
- groups
- devices
- telephone numbers
- other objects

A Directory Server (name server) is a server which provides a directory service

Each resource on the network is considered an object by the directory server. Info about resources is stored as collection of attributes for that resource/object

Well-known directory services:

- Domain Name Service (DNS)
  - the directory service for the internet
- Microsoft Active Directory
  - and Azure Active Directory
- Apache Directory Server
- Oracle Internet Directory (OID)
- OpenLDAP
- Cloud Identity
- JumpCloud

## Active Directory

Microsoft Active Directory Domain Services was introduced in Windows 2000 to allow organizations to manage multiple on-premise infrastructure components and systems using a single identity per user

A forest of domains and their child domains is broken down into organizational units per child domain, and each organizational unit is broken down into the users and resources for that organizational unit

## Identity Providers (IDPs)

Identity Provider = system entity that creates, maintains, and manages identity info and also provides authentication services to applications within a federation or distributed network

- A trusted provider of your user identity that lets you use authentication to access other services. Could be Facebook, Amazon, Google, Twitter, Github, LinkedIn

Federated Identity = method for linking user's identity across multiple separate identity management systems

OpenID = open standard and decentralized auth protocol, e.g. log into multiple social media platforms with a single Google or Facebook account

- OpenID is about providing who you are

OAuth2.0 = industry-standard protocol for auth. OAuth doesn't share password data but instead uses authorization tokens to prove an identity between consumers and service providers

- OAuth is about granting access to functionality

SAML = Security Assertion Markup Language, an open standard for exchanging authentication and authorization between an identity provider and service provider

- used for SSO via web browser

## Single Sign On

Single Sign-On (SSO) is an authentication scheme allowing users to log in with a single ID and password to different systems and software

- allows IT departments to adminster a single identity that can access many machines and cloud services

Login for SSO is mostly seamless, where once a user is logged into their primary directory, they do not see other login screens

## LDAP

Lightweight Directory Access Protocol (LDAP) = open, vendor-neutral, industry standard application protocol for accessing and maintaining distributed directory information services over an IP network

Common use of LDAP is to provide a central place to store usernames and passwords

LDAP enables same sign-on. Same sign-on allows users to use a single ID and password, but they have to enter it in every time they want to login

Why use LDAP when SSO is more convenient?

- most SSO systems are using LDAP
- LDAP not designed to work natively with web apps
- Some systems only support integration with LDAP and not SSO

## Multi-Factor Authentication (MFA)

MFA = security control where after you fill in your username/password, you have to use a second device such as a phone to confirm it is you logging in

- protects against people who have stolen your password
- an option in most cloud providers and social media websites

## Security Keys

Security Key = secondary device used as a second step in authentication process to gain access to a device, workstation, or app

Can resemble a memory stick. You press a button/exposed metail, and the device generates and autofills a security token

## AWS Identity and Access Management (IAM)

- create and manage AWS users and groups, and use permissions to allow/deny their access to AWS resources

IAM Policies = JSON documents which grant permissions for a specific user, group, or role to access services. Polices are attached to IAM identities

IAM Permission = API actions that can or cannot be performed. Represented in an IAM Policy document

IAM Users = end users to log into console or interact with AWS resources programmatically or via clicking UI interfaces

IAM Groups = Group up your users so they all share permission levels

IAM Roles = roles grant AWS resources permissions to specific AWS API actions. Associate policies to a role then assign it to an AWS resource

### Anatomy of an IAM Policy

- written in JSON, contain permissions which determine what API acctions are allowed/denied
  - version: policy language version
  - statement container: policy element, allowed to have multiples
  - Sid: optional way of labeling statements
  - Effect: whether policy will Allow or Deny
  - Action: list of actions that the policy allows/denies
  - Principal: account, user, role, or federated user to which you would like to allow/deny access
  - Resource: which resource(s) to which the action(s) applies
  - Condition: circumstances under which the policy grants permission

## Principle of Least Privilege (PoLP)

Principle of Least Privilege = computer security concept of providing a user, role, or application with the least amount of permissions to perform an operation or action

Just-Enough-Access (JEA) = permitting only the exact actions for the identity to perform a task

Just-In-Time (JIT) = permitting the smallest length of duration an identity can use permissions

Risk-based Adaptive Policies = each attempt to access a resource generates a risk score of how likely the request is to be from a compromised source. Based on many factors such as device, location, IP address, the service being accessed and time of day

- AWS does not have risk-based adaptive policies built into IAM (but Cognito does for user pools)
- Netflix open source project ConsoleMe is a self-service short-lived IAM policy tool for AWS resource access while enforcing JEA and JIT

## AWS Account Root User

Root User = special user with full access

- Created at time of AWS account creation
- uses email/password to login
- cannot be deleted
- full permissions to account and its permissions, and cannot be limited
- cannot use IAM policies to explicitly deny root user access to resources
- you can only use SCPs to limit permissions of the root user
- one root user per AWS account
- for very specific/specialized tasks that are infrequently or rarely performed
- strongly recommended to never use Root User access keys
- strongly recommended to turn on MFA for root user

Tasks only a root user can perform:

- change account settings
  - account name, email address, root user password, root user access keys
- restore IAM user permissions for an IAM admin that revokes their own permissions
- activate IAM access to Billing and Cost Management console
- view certain tax invoices
- close AWS account
- cancel or change AWS Support Plan
- register as seller in RI marketplace
- enable MFA Delete on an S3 Bucket
- Edit/Delete S3 policy including an invalid VPC ID or VPC endpoint ID
- Sign up for GovCloud
- Create organizations

## AWS Single Sign On

- create or connect workforce identities in AWS once and manage access centrally across your AWS organization
