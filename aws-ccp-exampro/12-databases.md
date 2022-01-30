# Databases

Database = a data store that stores semi-structured and structured data

A database is a more complex data store because it requires using formal design and modeling techniques

Databases can generally be categorized as:

- Relational Databases
  - structured data that strongly represents tabular data (tables, rows, columns)
  - row or column-oriented
- Non-relational Databases
  - semi-structured data that may or may not resemble tabular data

Rich set of functionality

- specialized languages to query/retrieve data
- specialized modeling strategies to optimize retrieval for different use cases
- fine tuned control over transformation of data into useful data structures or reports

Normally "databases" infers someone is using a relational row-oriented data store

## Data Warehouse

Data warehouse = relational datastore designed for analytic workloads. Generally column-oriented data-stores

Companies have terabytes and millions of rows of data and need fast ways to produce analytics reports

Data warehouses generally perform **aggregation**

- aggregation is grouping data (ie: to find a total or average)
- optimized around columns since they need to quickly aggregate column data

Data warehouses are generally designed to be hot, so they can return queries very fast even though they have vast amounts of data

Data warehouses are infrequently accessed, meaning they aren't intended for real-time reporting, but maybe once or twice per day, or once per week to generate business and user reports

Data warehouses need to be able to consume relational database or ETL data on a regular basis

## Key Value Stores

A key-value database is a type of non-relational database (NoSQL) that uses a simple key-value method to store data

- dumb and fast
- generally lack features like:
  - relationships
  - indexes
  - aggregation

Key-value stores can resemble tabular data, but do not have the consistency to columns/rows (schemaless)

Due to their simple design, they can scale well beyond a relational database

## Document Stores

A document store is a NoSQL database that stores documents as its primary data structure

- a document could be XML, but more commonly is JSON or JSON-like
- document stores are a sub-class of key-value stores
- components of a document store have mapping to components in relational databases

| Relational |       Document        |
| :--------: | :-------------------: |
|   Tables   |      Collection       |
|    Rows    |       Documents       |
|  Columns   |        Fields         |
|  Indexes   |        Indexes        |
|   Joins    | Embedding and Linking |

## NoSQL Database Services

- DynamoDB = serverless NoSQL key/value and document database. Designed to scale to billions of records with guaranteed consistent data return in at least a second. No shard management!
  - flagship AWS database service - scales, is cost effective, and very fast
  - in 2019 Amazon online retail shut down the last of their Oracle databases, completing their migration to DynamoDB. Reduced costs by 60% and latency by 40%
  - use when you want a massively scalable database
- DocumentDB = no SQL document database that is MongoDB compatible
  - use when you want a MongoDB database
- Amazon Keyspaces = fully managed Apache Cassandra database (columnar store, similar to DynamoDB with some additional functionality)
  - use when you want to use Apache Cassandra

## Relational Database Services

- Relational Database Services (RDS) = relational database service supporting multiple SQL engines. Relational is synonymous with SQL and Online Transactional Processing (OLTP). The most commonly used type of database among tech companies and startups

  - RDS supports the following SQL engines:
    - MySQL - open-source SQL database, bought by Oracle
    - MariaDB - fork of MySQL under different open-source license after Oracle purchase of MySQL
    - Postgres (PSQL) - open-source SQL database with rich features over MySQL with added complexity
    - Oracle - Oracle's proprietary SQL database. Have to buy a license to use it. Common in enterprise companies
    - Microsoft SQL Server - Microsoft's proprietary SQL database. Have to buy a license to use it

- Aurora - fully managed database

  - Aurora
    - either MySQL (5x faster) or Postgres (3x faster)
    - when you want a highly available, durable, scalable, and secure relational database for Postgres or MySQL
  - Aurora Serverless
    - serverless on-demand version of Aurora
    - when you want "most" of the benefits of Aurora, but can trade to have cold-starts or don't have lots of traffic demand

- RDS on VMWare = allows you to deploy RDS supported engines to an on-premise data-center. Datacenter must be using VMWare for server virtualization
  - when you want databases managed by RDS on your own datacenter

## Other Database Services

- Redshift - petabyte-size data warehouse
  - when you want to quickly generate analytics/reports from a large amount of data
- ElastiCache - managed database of in-memory and caching open-source database Redis or Memcached
  - when you need to improve app performance by adding a caching layer in front of web server or database
- Neptune - managed graph database. Data represented as interconnected nodes
  - when you need to understand the connections between data
- Amazon Timestreams - fully managed time-series database
  - when you need to measure how things change over time
- Amazon Quantum Ledger Database - fully managed ledger database providing transparent, immutable, and cryptographically verifiable transaction logs
  - when you need to record the history of financial activities that can be trusted
- Database Migration Service (DMS) - database migration service used to migrate between databases
  - on-premise DB to AWS
  - two databases in different or same AWS accounts using different engines
  - from SQL to NoSQL
