---
title : "Manage using AWS Management Console"
date :  "`r Sys.Date()`" 
weight : 1 
chapter : false
pre : " <b> 2.1 </b> "
---
You can access the AWS management console for Amazon DynamoDB at [AWS management console for Amazon DynamoDB](https://console.aws.amazon.com/dynamodb/home).

You can use the  management console to do the following things in DynamoDB:

- Track recent alerts, total capacity, service health, and the latest DynamoDB news on the DynamoDB console.

- Create, update and delete tables. The capacity calculator provides an estimate of the number of capacity units required based on the usage information you provide.

- Stream management.

- View, add, update and delete entries stored in the table. **Time to Live (TTL)** to determine when table entries expire so they can be automatically deleted from the database.

- Query and scan tables.

- Set up and view alerts to monitor table capacity usage. View your table's top monitoring metrics on a real-time chart from **CloudWatch**.

- Modify the provided capacity of the table.

- Modify the table class of the table.

- Create and delete global Secondary Indexes.

- Create triggers to connect DynamoDB streams to AWS Lambda functions.

- Apply tags to your resources to help organize and identify them.

- Buy reserve capacity.

{{% notice info %}}
If you can predict your need for Amazon DynamoDB read-and-write throughput, reserved capacity offers significant savings over the normal price of DynamoDB provisioned throughput capacity. You pay a one-time upfront fee and commit to paying for a minimum usage level at specific hourly rates for the duration of the reserved capacity term.
{{% /notice %}}

![DYNAMODB AWS](/images/2-prerequisite/2.1-useawsconsole/0001-dynamodbhome.png)

Management console shows an intro screen prompting you to create your first table. To view your tables, in the navigation bar on the left side of the table panel, select **Tables** .

Here is a high-level overview of the tasks available per table in each navigation tab:

- **Overview** - View table details, including item count and metrics.

- **index** - Manage global and local secondary indexes.

- **Monitoring** - View alarms, CloudWatch collaborator Insights, and Cloudwatch metrics.

- **Global table** - Manage table copy.

- **Backup** - Manage restores in time and backups on demand.

- **Export & Stream** - Export your tables to Amazon S3 and manage DynamoDB Streams and Kinesis Data Streams.

- **Additional Settings** - Manage read/write capacity, Duration settings, encryption and tags.