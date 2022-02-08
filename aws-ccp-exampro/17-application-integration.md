# Application Integration

Application Integration = process of letting two independent applications communicate and work with each other, commonly facilitated by an intermediate system

Loose coupling is desirable for cloud systems/services, so AWS has many services designed around app integration

Common patterns include:

- queueing
- streaming
- pub/sub
- API gateways
- state machine
- event bus

## Queueing and SQS

Messaging system = system for providing async communication to decouple processes via messages/events from a sender and receiver (producer and consumer)

Queueing System = messaging system that generally will delete messages once they are consumed. Simple communication. Not real-time. Have to pull. Not reactive

Simple Queueing Service (SQS) = fully managed queueing service that enables decoupling and scaling microservices, distributed systems, and serverless apps

- use case: queue up transactional emails to be sent (signup, reset password)

## Streaming

Streaming = multiple consumers can react to events/messages

Events live in the stream for long periods of time, so complex operations can be applied. Real-time

Amazon Kinesis = fully managed solution for collecting, processing, and analyzing streaming data in the cloud. Does more work than a queuing system, but also costs more

## Pub / Sub

Publish/subscribe pattern = sender of messages (publishers) do not send their messages directly to receivers. Instead, send messages to an event bus, which categorizes their messages into groups. Receivers (subscribers) subscribe to these groups. Whenever new messages appear within their subscriptions, the messages are immediately delivered to them.

- publishers have no knowledge of who their subscribers are
- subscribers do not pull for messages
- messages are automatically and immediately pushed to subscribers
- messages/events are interchangeable terms in pub/sub

Use Case: real time chat system or webhook system

Simple Notification System (SNS) = highly available, durable, secure, fully managed pub/sub messaging system that enables decoupled microservices, distributed systems, and serverless apps

## API Gateway

An API Gateway is a program that sits between a single entry point and multiple backends. Allows for throttling, logging, routing logic, or formatting of request/response

Amazon API Gateway = solution for creating secure APIs in cloud at any scale. Create APIs that act as a front door for apps to access data, business logic, or backend service functionality

## State Machines / Step Functions

State machine = abstract model which decides how one state moves to another based on a series of conditions. Like a flow chart

AWS Step Functions = coordinate multiple AWS services into a serverless workflow

- a graphical console to visualize the components of your app as a series of steps
- automatically triggers and tracks each step, retries when erroring, so app executes in order and as expected, always
- logs state of each step to improve debugging

## Event Bus

Event Bus = system that receives events from a source and routes events to a target, based on rules

EventBridge = serverless event buss service used for application integration by streaming real-time data to apps (used to be known as CloudWatch events)

Event Bus -> holds event data, define rules to react to events
Default Event Bus -> AWS account has a default event bus
Custom Event Bus -> scoped to multiple accounts or other AWS accounts
SaaS Event Bus -> Scoped to with 3rd party SaaS providers
Producers -> AWS Services that emit events
Events -> data emitted by services. JSON objects that travel (stream) within the event bus
Partner Sources -> 3rd party apps that can emit events to the bus
Rules -> Determine what events to capture and pass to targets (100 rules/bus)
Targets -> AWS Services that consume events (5 targets/rule)

## Application Integration Services

SNS -> Pub/Sub messaging system. Plain-text, email, HTTP/S (webhooks), SQS, and Lambda. Pushes messages sent to subscribers

SQS -> queuing messaging system. Send events to queue. Other apps pull the queue for messages. Commonly used for background jobs

Step Functions -> State machine service. Coordinate multiple AWS services into serverless workflows. Easily share data among lambdas. Have group of lambdas wait for each other. Create logical steps. Works with Fargate tasks

EventBridge -> serverless event bus. Connect apps from various application, 3rd party services, and AWS services

Kinesis = real-time streaming data service. Create producers which send data to a stream. Multiple consumers can consume data within a stream. Real-time analytics, click stream, ingesting data from a fleet of IOT devices

Amazon MQ = managed broker service using Apache ActiveMQ

Managed Kafka Service (MSK) = fully managed Apache Kafka service. Kafka is open source platform for real-time streaming data pipelines and apps. Similar to Kinesis but more robust

API Gateway = fully managed service for create/publish/maintain/monitor/secure APIs. Create API endpoints and route them to AWS services

AppSync = fully managed GraphQL service. GraphQL is open-source agnostic query adaptor allowing query of data from many different data sources
