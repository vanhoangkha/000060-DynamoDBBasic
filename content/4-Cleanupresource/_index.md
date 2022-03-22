---
title : "Clean up resource"
date :  "`r Sys.Date()`" 
weight : 4
chapter : false
pre : " <b> 4. </b> "
---

### Using AWS Management Console

   1. Open the DynamoDB console table at https://console.aws.amazon.com/dynamodb/

   2. In the navigation bar on the left side of the panel, select **Tables**

   3. Select the **Music** board from the list of boards.

   4. Select **Actions**, then select **Delete table**.



![Delete Table!](/images/2-prerequisite/4.cleanupresource/0001-cleanup.png "Delete Table")


### Using AWS CloudShell

- To delete a table, use the command **`delete-table`**

- Type command:
  
```
aws dynamodb delete-table --table-name Music
```