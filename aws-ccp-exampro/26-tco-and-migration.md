# TCO and Migration

## Total Cost of Ownership (TCO)

TCO = financial estimate intended to help buyer and owners determine the direct and indirect costs of a product or service. Includes items like:

- Hardware
- Taxes
- Licensing
- Security
- Software
- Training
- IT Personnel
- Installation
- Monitoring

Creating a TCO report is useful when looking to migrate from on-premise to the cloud

Cloud services can initially be more expensive than running on-premises data centers. They can, however, become cost-effective over time if organizations learn to use and operate them more efficiently

CAPEX (On-Premise)

- software license fees
- implementation
- configuration
- training
- physical security
- hardware
- IT personnel
- maintenance

OPEX (AWS)

- subscription fees
- implementation
- configuration
- training

AWS claims up to 75% savings on TCO

### CAPEX vs. OPEX

CAPEX = Capital Expenditure. Spend money upfront on physical infrastructure, deducting that expense from your tax bill over time

- server costs
- storage costs
- network costs
- backup and archive costs
- disaster recovery costs
- datacenter costs
- technical personnel

With CAPEX, you have to guess upfront what you plan to spend

OPEX = Operational Expenditure. Costs associated with an on-premises datacenter have been shifted to the service provider. Customer is only concerned with non-physical costs

- leasing software and customizing features
- training employees in cloud services
- paying for Cloud Support
- billing based on cloud metrics
  - compute usage
  - storage usage

With OPEX, you can try a product or service without investing in equipment

### Shifting IT Personnel

Does Cloud make IT Personnel Redundant?

- a company needs IT personnel during the migration phase
- a company can transition some roles to new cloud roles
  - networking to Cloud Networking
- a company may decide to take a Hybrid approach, and will always need traditional IT and Cloud IT
- a company can change employee activities from **Managing Infrastructure to Revenue Generating**

### AWS Pricing Calculator

Free cost estimate tool used to estimate the cost of various AWS services. No account needed.

- contains 100+ services to configure for cost estimates
- need to compare existing cost against AWS costs for TCO, the calculator can help with that
- export final estimate to CSV

## Migration Evaluator

AWS Migration Evaluator (formerly known as TSO Logic) is an estimate tool used to determine an organization's existing on-premise cost so it can compare it against AWS costs for a planned cloud migration

Migration Evaluator uses an Agentless Collector to collect data from your on-premise infrastructure to extract your on-premise cost

## EC2 VM Import/Export

VM Import/Export allows users to import VM images into EC2

AWS can import from:

- VMWare
- Citrix
- Microsoft Hyper-V
- Windows VHD from Azure
- Linux VHD from Azure

Process:

1. Prepare Virtual Image for upload
2. Upload Virtual Image to S3
3. Use AWS CLI to import image, which generates an AMI you can use to launch an EC2

## Database Migration Service (DMS)

Allows quick and secure migration of one database to another. Can be used for on-premise to AWS

Possible Sources:

- Oracle DB
- Microsoft SQL
- MySQL
- MariaDB
- PostgreSQL
- MongoDB
- SAP ASE
- IMDB Db2
- Azure SQL Database
- Amazon RDS
- Amazon S3 (database dumps)
- Amazon Aurora

Possible Targets:

- Oracle DB
- Microsoft SQL
- MySQL
- MariaDB
- PostgreSQL
- Redis
- SAP ASE
- Amazon RDS
- Amazon DynamoDB
- Amazon S3
- Amazon Aurora
- Amazon OpenSearch Service
- Amazon ElastiCache for Redis
- Amazon DocumentDB
- Amazon Neptune
- Apache Kafka

AWS Schema Conversion Tool is used in many causes to automatically convert a source DB schema to a target DB schema

Each migration path requires research since not all combinations of sources and targets are possible
