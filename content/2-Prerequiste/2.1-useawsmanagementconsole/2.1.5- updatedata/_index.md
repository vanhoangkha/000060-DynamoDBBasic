---
title : " Update data"
date :  "`r Sys.Date()`" 
weight : 5
chapter : false
pre : " <b> 2.1.5 </b> "
---

The steps to update the Music table data are as follows:

1. Sign in to the AWS Management Console and open the DynamoDB Console at [DynamoDB Management Console](https://console.aws.amazon.com/dynamodb/).

2. In the navigation bar on the left side of the panel, select **Tables**

3. Select the **Music** board from the list of boards.

4. Select **Actions**, then select **Explore item**.

![Update Data Dashboard!](/images/2-prerequisite/2.1.5-updatedata/0001-updatedata.png "UpdateData")

5. Select item with **Artist** value of **`Acme Band`** and **SongTitle** value of **`Happy Day`**.

![Update Data Dashboard!](/images/2-prerequisite/2.1.5-updatedata/0002-updatedata.png "UpdateData")

6. Update the **Album Title** value to **Updated Album Title**, then select **Save changes**.

![Update Data Dashboard!](/images/2-prerequisite/2.1.5-updatedata/0003-updatedata.png "UpdateData")

7. Results after updating data:

![Read Data Dashboard!](/images/2-prerequisite/2.1.5-updatedata/0004-updatedata.png "ReadData")