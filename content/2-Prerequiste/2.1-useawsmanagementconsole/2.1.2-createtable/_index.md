---
title : "Create a table"
date :  "`r Sys.Date()`" 
weight : 2
chapter : false
pre : " <b> 2.1.2 </b> "
---

In this step, you create a Music table in Amazon DynamoDB. The table has the following details:

- **Partition key** — Artist

- **Sort key** — SongTitle

1. Sign in to the AWS Management Console and open the DynamoDB Console at [DynamoDB Management Console](https://console.aws.amazon.com/dynamodb/).

2. In the navigation bar on the left side of the panel, select **Dashboard**.

3. On the right side of the panel, select **Create Table**.

![Create Table Dashboard!](/images/2-prerequisite/2.1.2-createtable/0001-createtable.png "CreateTableDashboard")

4. Enter the table details as follows:

- For **Table name**, enter **``` Music ```**.

- For **Partition key**, enter **```Artist```**.

- Enter **SongTitle** as **Sort key**.

- Select **Default settings**.
  
![Create Table Dashboard!](/images/2-prerequisite/2.1.2-createtable/0002-createtable.png "CreateTableDashboard")

5. Select **Create table** to create the table.

![Create Table Dashboard!](/images/2-prerequisite/2.1.2-createtable/0003-createtable.png "CreateTableDashboard")