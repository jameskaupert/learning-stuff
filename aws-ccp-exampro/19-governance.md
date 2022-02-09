# Governance

## Organizations and Accounts

AWS Organizations = allows creation of new AWS accounts. Centrally manage billing, control access, compliance, security, and share resources across your AWS accounts

Root Account User = the only sign in identity that has complete access to all AWS services and resources in an account. Each account has a Root Account User

Organizational Units = group of AWS accounts within an organization which can also contain other organizational units, creating a hierarchy

Service Control Policies = gives central control over allowed permissions for all accounts in your organization, helping to ensure your accounts stay within your organization's guidelines (IAM policies defined for an entire organization or account(s))

AWS Organizations must be turned on, and cannot be turned off once on

You can create as many AWS Accounts as you like - one will be the Master/Root account
