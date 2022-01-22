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
