---
title : "Primary Key"
date :  "`r Sys.Date()`" 
weight : 2
chapter : false
pre : " <b> 1.2 </b> "
---

![Core Components of Amazon DynamoDB](/images/1-introduce/1.1-corecomponentsofamazondynamodb/0001-Diagram-DynamoDB-Tables.png)

- When you create a table, in addition to the table name, you must specify the **primary key** of the table.
The primary key uniquely identifies each item in the table, so no two items can have the same key.
DynamoDB supports two different types of primary keys:
+ **Partition key**
+ **Composite primary key**
  
#### **Partition key**
- A simple primary key, consisting of an attribute called **Partition key**.
- **DynamoDB** uses the value of the partition key as input to the internal hash. The output from the hash defines the partition (physical memory inside DynamoDB) in which the item will be stored.
In a table with only a partition key, no two items can have the same partition key value.

#### **Composite primary key**
- The first attribute is **partition key** and the second attribute is **sort key**.
- **DynamoDB** uses the partition key value as input to the internal hash. The output from the hash defines the partition (physical memory inside DynamoDB) in which the item will be stored. All items with the same partition key value are stored together, in sorted order by the sort key value.
In a table with a partition key and a sort key, multiple items can have the same partition key value. However, those items must have different sort key values.
- **Composite primary** key gives you more flexibility when querying data.
