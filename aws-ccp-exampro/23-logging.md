# Logging Services

CloudTrail = logs all API calls (SDK/CLI) between AWS services (who can we blame)

- who created this bucket?
- who spun up that expensive EC2 instance?
- who launched this SageMaker notebook?
- detect developer misconfiguration
- detect malicious actors
- automate responses

CloudWatch = collection of multiple services

- CloudWatch Logs = centralized place to store clloud services log data or application logs
- CloudWatch Metrics = represents a time-ordered set of data points. A variable to monitor and alert on
- CloudWatch Events (EventBridge) = trigger an event based on a condition
- CloudWatch Alarms = trigger notifications based on metrics
- CloudWatch Dashboard = create visualizations based on metrics

AWS X-Ray = distributed tracing system. Pinpoint issues with microservices. See how data moves from one app to another, how long it took to move, and if it failed to move forward

## CloudTrail

CloudTrail = service enabling governance, compliance, operational auditing, and risk auditing of AWS accounts

- used to monitor API calls and actions made on an AWS account
  - Where: sourceIPAddress
  - When: EventTime
  - Who: User, UserAgent
  - What: Region, Resource, Action

Default logging for 90 days via Event History

- need to create a Trail if you want more than 90 days

Trails are output to S3 and do not have a GUI like Event History does. To analyze a Trail, use Amazon Athena

## CloudWatch Alarms

CloudWatch Alarm = monitors a CloudWatch Metric, based on a defined threshold. When an alarm breaches (goes outside the threshold), the alarm changes state

- OK = metric / expression is within the defined threshold
- ALARM = metric / expression is outside of the defined threshold
- INSUFFICIENT_DATA = alarm has just started, the metric is not available, or not enough data is available

When the alarm changes state, we can define what action it should trigger

- notification
- ASG
- EC2 Action
