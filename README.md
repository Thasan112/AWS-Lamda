# AWS-Lamda
Serverless reporting pipeline using AWS Lambda, EventBridge, and SNS to query an EC2 LAMP database via SSM Parameter Store credentials.


## Project Overview

This repository demonstrates an automated, event-driven serverless reporting solution built on AWS. 

The application automatically generates and emails a daily Sales Analysis Report to stakeholders without requiring manual intervention or dedicated long-running servers. 

### How It Works:
1. **Scheduled Trigger:** An Amazon EventBridge rule initiates the main orchestrator Lambda function on a daily schedule.
2. **Secure Credentials Retrieval:** The Lambda function fetches database connection parameters from **AWS Systems Manager (SSM) Parameter Store**, keeping secrets separated from application code.
3. **Data Extraction:** The function connects over the network to a MySQL database running on an **Amazon EC2 LAMP instance** to run analytical sales queries.
4. **Report Notification:** The extracted query results are formatted into a report and published to an **Amazon SNS** topic, which automatically emails the final report to subscribed recipients.

### Key Skills Demonstrated:
* **Serverless Architecture & Event-Driven Automation**
* **Decoupled Secrets & Configuration Management** (SSM Parameter Store)
* **VPC & Database Networking** (Lambda to EC2 connection)
* **Least-Privilege Security** (IAM policies for Lambda execution roles)
