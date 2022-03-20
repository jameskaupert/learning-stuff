# Provisioning Services

Provisioning = allocation or creation of resources and services to a customer

AWS provisioning services are responsible for setting up and then managing those AWS services

Elastic Beanstalk = Platform as a Service to easily deploy web applications. Provisions various AWS services including EC2, S3, SNS, CloudWatch, ASGs, ELBs. Similar to Heroku

AWS OpsWorks = configuration management service that also provides managed instances of the open-source configuration managed software Chef and Puppet

Cloudformation = infrastructure modeling and provisioning service. Automate the provisioning of AWS services by writing CloudFormation templates in either JSON or YAML (Infrastructure as Code / IAC)

AWS Quickstarts = premade packages that can launch/configure your AWS compute, network, storage, and other services required to deploy a workload on AWS

AWS Marketplace = digital catalog of thousands of software listings from independent vendors

AWS Amplify = mobile/web framework to provision multiple AWS services as your backend (serverless)

AWS App Runner = fully managed service that makes it easy to deploy containerized web apps and APIs at scale

AWS Copilot = CLI enabling quick launch/management of containerized apps

AWS CodeStar = unified interface for managing software development activities in one place. Easily launch common types of stacks like LAMP

AWS Cloud Development Kit = IAC using programming language to generate Cloudformation templates

## Elastic Beanstalk

Platform as a Service (Paas) = customers can develop, run, and manage applications without the complexity of building and maintaining the infrastructure typically associated with developing and launching an app

Elastic Beanstalk is a PaaS for deploying web applications with little knowledge of the underlying infrastructure so you can focus on writing application code instead of setting up an automated deployment pipeline and DevOps tasks. Choose a platform, upload your code, and run it with little knowledge of the infrastructure

Powered by Cloudformation templates

- Elastic Load Balancer
- Autoscaling Groups
- RDS database
- EC2 instance preconfigured or custom
- Monitoring (CloudWatch, SNS)
- In-Place and Blue/Green deployment methodologies
- Security (rotates passwords)
- Can run Dockerized environments
