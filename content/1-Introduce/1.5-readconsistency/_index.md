---
title : "Read Consistency"
date :  "`r Sys.Date()`" 
weight : 5
chapter : false
pre : " <b> 1.5</b> "
---

#### **Eventually Consistent Reads**
- When you read data from a DynamoDB table, the response may not reflect the result of a recently completed write operation.
- Responses may include some stale data.
- If you repeat your read request after a short time, the response will return the latest data.

#### **Strongly Consistent Reads**
When you request **Strongly Consistent Reads**, **DynamoDB** returns a response with the most up-to-date data, reflecting updates from all previous writes that were successful. However, this consistency comes with some downsides:
- **Strongly Consistent Reads** may not be available if there are network problems or outages. In this scenario, **DynamoDB** may return **server error (HTTP 500)**.
- **Strongly Consistent Reads** may have higher latency than **eventually consistent reads**.
- **Global secondary indexes** are not supported **Strongly Consistent Reads**.
- **Strongly Consistent Reads** uses double throughput capacity than **eventually consistent reads**.