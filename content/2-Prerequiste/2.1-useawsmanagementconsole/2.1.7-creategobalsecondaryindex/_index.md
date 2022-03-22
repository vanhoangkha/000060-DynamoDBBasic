---
title : "Create a Global Secondary Index"
date :  "`r Sys.Date()`" 
weight : 7
chapter : false
pre : " <b> 2.1.7 </b> "
---

1. Sign in to the AWS Management Console and open the DynamoDB Console at [DynamoDB Management Console](https://console.aws.amazon.com/dynamodb/).

2. In the navigation bar on the left side of the panel, select **Tables**

3. Select the **Music** board from the list of boards.

![Create Global Secondary Index!](/images/2-prerequisite/2.1.7-creategobalsecondaryindex/0001-creategobalsecondaryindex.png "Create Global Secondary Index")

4. Select the **Indexes** tab from the **Music** panel.

5. Select **Create index**
   
![Create Global Secondary Index!](/images/2-prerequisite/2.1.7-creategobalsecondaryindex/0002-creategobalsecondaryindex.png "Create Global Secondary Index")

6. For **Partition key** , enter **`AlbumTitle`**.

7. For **Index name**, enter **`AlbumTitle-index`**.

![Create Global Secondary Index!](/images/2-prerequisite/2.1.7-creategobalsecondaryindex/0003-creategobalsecondaryindex.png "Create Global Secondary Index")

8. Leave other items as default and select **Create index**

![Create Global Secondary Index!](/images/2-prerequisite/2.1.7-creategobalsecondaryindex/0004-creategobalsecondaryindex.png "Create Global Secondary Index")

9. Result:

![Create Global Secondary Index!](/images/2-prerequisite/2.1.7-creategobalsecondaryindex/0005-creategobalsecondaryindex.png "Create Global Secondary Index")