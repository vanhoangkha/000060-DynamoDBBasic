---
title : "Core Components of Amazon DynamoDB"
date :  "`r Sys.Date()`" 
weight : 1 
chapter : false
pre : " <b> 1.1 </b> "
---

![Core Components of Amazon DynamoDB](/images/1-introduce/1.1-corecomponentsofamazondynamodb/0001-Diagram-DynamoDB-Tables.png)

- **Table**: Similar to other database systems, DynamoDB stores data in tables. The table is a collection of items. 

- **Item**: Each table contains zero or more items. Items in DynamoDB are quite similar to the concept of rows in relational databases, records, or tuples in other database systems. In DynamoDB, there is no limit to the number of items you can store in a table.

- **Attribute**: Each item includes one or more attributes. An attribute is a basic data element that does not need to be broken down further. Attributes in DynamoDB are in many ways similar to columns in other database systems.

