---
title : "Query the Global Secondary Index"
date :  "`r Sys.Date()`" 
weight : 8
chapter : false
pre : " <b> 2.1.8 </b> "
---

1. Sign in to the AWS Management Console and open the DynamoDB Console at [DynamoDB Management Console](https://console.aws.amazon.com/dynamodb/).
2. In the navigation bar on the left side of the panel, select **Tables**
3. Select the **Music** board from the list of boards.
4. Select **Actions**, then select **Explore item**.

![Query Global Secondary Index!](/images/2-prerequisite/2.1.8-querytheglobalsecondaryindex/0001-querytheglobalsecondaryindex.png "Query Global Secondary Index")

5. Select **Query**
6. In the drop-down list below **Query**, select **AlbumTitle-index**
7. For **AlbumTitle** , enter **`Somewhat Famous`**, .
8. Select **Run**
9. Return result:
  
![Query Global Secondary Index!](/images/2-prerequisite/2.1.8-querytheglobalsecondaryindex/0002-querytheglobalsecondaryindex.png "Query Global Secondary Index") 