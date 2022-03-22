---
title : "Query data"
date :  "`r Sys.Date()`" 
weight : 6
chapter : false
pre : " <b> 2.1.6 </b> "
---

The steps to query the **Music** table data are as follows:

1. Sign in to the AWS Management Console and open the DynamoDB Console at [DynamoDB Management Console](https://console.aws.amazon.com/dynamodb/).


2. In the navigation bar on the left side of the panel, select **Tables**

3. Select the **Music** board from the list of boards.

4. Select **Actions**, then select **Explore item**.
  
![Query Data Dashboard!](/images/2-prerequisite/2.1.6-querydata/0001-querydata.png "UpdateData")

5. Select **Query**

6. Enter the details of the keys:

- For **Artist (Partition key)**, enter **`Acme Band`**

- For **SongTitle (Sort key)**, enter **`PartiQL Rocks`**

7. Select **Run**
8. Return result:

![Query Data Dashboard!](/images/2-prerequisite/2.1.6-querydata/0002-querydata.png "UpdateData")