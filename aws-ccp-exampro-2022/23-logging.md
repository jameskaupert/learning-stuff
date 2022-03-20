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

### Anatomy of an Alarm

Threshold Condition = defines when a datapoint is breached

Metric = the actual data being measured

Period = how often to check/evaluate the alarm

Data point = metric measurement at a given period

Evaluation Periods = number of previous periods

Datapoints to Alarm = criteria to alarm on (ie: 1 datapoint breach across 4 periods, etc...)

## Log Streams

Log stream = sequence of events from an application or instance being monitored

Log Event = single event in a log file. Seen within a Log Stream

- can filter events based on simple or pattern matching syntax

## Log Insights

Log Insights enables you to interactively search and analyze CloudWatch log data

- more robust filtering than simple filter events in a Log Stream
- less burdonsome than having to export logs to S3 and analyze in Athena
- Supports all types of logs
- commonly used via the console to do ad-hoc queries against log groups
- has its own language called CloudWatch Logs Insights Query Syntax
- single request can query up to 20 log groups
- Queries time out after 15 minutes, if they have not completed
- Query results available for 7 days
- create and save queries to make future repetitive tasks easier

AWS provides sample queries to help get started and learn Query Syntax

## CloudWatch Metrics

CloudWatch Metric = time-ordered set of data points

- variable that is monitored over time

CloudWatch comes with many pre-defined metrics that are generally namespaced by their AWS Service

EC2 Per-Instance Metrics

- CPUUtilization
- DiskReadOps
- DiskWriteOps
- DiskReadBytes
- DiskWriteBytes
- NetworkIn
- NetworkOut
- NetworkPacketsIn
- NetworkPacketsOut

Used by CloudWatch Alarms and CloudWatch Dashboards
