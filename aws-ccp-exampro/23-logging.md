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
