---
title : "Secondary Index"
date :  "`r Sys.Date()`" 
weight : 3
chapter : false
pre : " <b> 1.3</b> "
---

![Secondary Index](/images/1-introduce/1.3-secondaryindexes/0001-Diagram-Local-Secondary-Indexs.png)

- You can create one or more **Secondary Index** on a table.
- Secondary Index allows to query data in the table with different keys from the original partition key and sort of the table. With Dynamo DB, data query operation is much faster and more cost-effective than scanning.
- DynamoDB doesn't force you to use indexes, but they do give your applications more flexibility when it comes to data queries. After creating a Secondary Index on the table, you can read data from the index in the same way as reading data from the table.

![Secondary Index](/images/1-introduce/1.3-secondaryindexes/0002-Diagram-Global-Secondary-Indexs.png)

DynamoDB supports two types of indexes:
- **Global secondary index** index has partition key and sort key may be different from indexes on table.
- **Local secondary index** index has the same partition key as the table but has a different sort key.

- Each table in DynamoDB has a maximum of **20 Global secondary indexes** (default limit) and **5 Local secondary indexes**.