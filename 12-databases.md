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
