---
title : "Read/Write Capacity Mode"
date :  "`r Sys.Date()`" 
weight : 6 
chapter : false
pre : " <b> 1.6</b> "
---

#### **On-Demand Mode**

- **Amazon DynamoDB on-demand** is a flexible payment option capable of serving thousands of requests per second without capacity planning. **DynamoDB** on-demand offers pay-on-demand for read and write requests so you only pay for what you use.
- When you select on-demand mode, **DynamoDB** instantly responds to your workloads as they increase or decrease to whatever traffic level was previously reached. If the workload's throughput reaches a new peak, DynamoDB adapts quickly to accommodate the workload. Tables using on-demand mode offer the same single-digit millisecond latency, service level agreement (SLA) commitment, and security that DynamoDB already provides. You can choose on demand for both new and existing tables, and you can continue to use existing **DynamoDB** APIs without code changes.
- On-Demand mode is a good choice if any of the following are true:
  + You create a new board with an unknown workload.
  + You have unpredictable application traffic.
  + You just love the ease of paying for what you use.


![Scan](/images/1-introduce/1.6-readwritecapacitymode/0001-Diagram-Scan.png)

#### **Provisioned Mode**
- If you select provisioned mode, you specify the number of reads and writes per second that you require for your application. You can use auto-scaling to automatically adjust your table's provisioned capacity in response to changes in traffic. This helps you manage your DynamoDB usage to stay at or below the specified request rate for cost predictability.
- The mode provided is a good option if any of the following are true:
  + You have predictable application traffic.
  + You run applications with consistent or incremental traffic.
  + You can forecast capacity requirements to control costs.