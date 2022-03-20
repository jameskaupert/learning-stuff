# Serverless Services

Serverless = underlying servers, infrastructure and OS taken care of by cloud service provider. Generally HA by default, scalable, and cost-effective (pay for what you use)

DynamoDB = serverless NoSQL key/value and document database. Designed to scale to billions of recorsd with guaranteed consistent data return in <1s. Do not have to worry about managing shards

Simple Storage Service (S3) = serverless object storage service. Upload very large and unlimited files. Pay for what you store. Don't worry about underlying file system or upgrading disk size

ECS Fargate = serverless container orchestration service. Same as ECS, except you pay on-demand per running container instead of keeping an EC2 running even if you have no containers running. AWS manages the underlying server, so you don't need to scale / upgrade the EC2 server

AWS Lambda = serverless functions service. Run code w/o provisioning / managing servers. Upload small pieces of code, choose memory and function timeout. Charged on runtime of function rounded to nearest 100ms.

Step Functions = state machine service. Coordinate multiple AWS services into serverless workflows. Easily share data among lambdas. Have group of lambdas wait for each other and create logical steps. Also works with Fargate Tasks

Aurora Serverless = serverless on-demand version of Aurora. When you want "most" of the Aurora benefits but can trade to have cold starts or don't have lots of traffic demand

## Serverless Architecture

Serverless architecture = fully managed cloud services. Generally not a "is serverless or not", but on a scale, where something is "a degree of serverless". Everyone defines serverless differently.

Could have all or most of the following characteristics:

- highly elastic and scalable
- highly available
- highly durable
- secure by default
- abstracts away underlying infrastructure, and billing is based on execution of the task
- scale to zero - resources cost nothing when not in use
