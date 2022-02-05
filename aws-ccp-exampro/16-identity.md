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
