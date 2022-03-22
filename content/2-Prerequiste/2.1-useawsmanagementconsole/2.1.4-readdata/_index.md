---
title : " Read data"
date :  "`r Sys.Date()`" 
weight : 4
chapter : false
pre : " <b> 2.1.4 </b> "
---

Steps to read data from Music table using DynamoDB console:

1. Sign in to the AWS Management Console and open the DynamoDB Console at [DynamoDB Management Console](https://console.aws.amazon.com/dynamodb/).

2. In the navigation bar on the left side of the panel, select **Tables**

3. Select the **Music** board from the list of boards.

4. Select **Actions**, then select **Explore items**.
  
![Read Data Dashboard!](/images/2-prerequisite/2.1.4-readdata/0001-readdata.png "ReadData")

5. Select **Query**, then enter **Artist (Partition key)** as **`Acme Band`**
   
![Read Data Dashboard!](/images/2-prerequisite/2.1.4-readdata/0002-readdata.png "ReadData")

6. Select **Run** and get the results as shown:
  
![Read Data Dashboard!](/images/2-prerequisite/2.1.4-readdata/0003-readdata.png "ReadData")