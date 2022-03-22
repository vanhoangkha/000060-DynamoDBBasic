---
title : "Write data"
date :  "`r Sys.Date()`" 
weight : 3
chapter : false
pre : " <b> 2.1.3 </b> "
---

Steps to record data to the Music table (created in section 2.1.2):

1. Sign in to the AWS Management Console and open the DynamoDB Console at [DynamoDB Management Console](https://console.aws.amazon.com/dynamodb/).

2. In the navigation bar on the left side of the panel, select **Tables**.

3. In the list of boards, select the **Music** board.
   
4. Select **Explore items**

![Write Data Dashboard!](/images/2-prerequisite/2.1.3-writedata/0001-writedata.png "WriteData")

5. In the **Items** interface, select **Create item**

![Write Data Dashboard!](/images/2-prerequisite/2.1.3-writedata/0002-writedata.png "WriteData")

6. Select **Add new attribute**, then select **Number**. School name: **Awards**.

![Write Data Dashboard!](/images/2-prerequisite/2.1.3-writedata/0003-writedata.png "WriteData")

7. Repeat step 6 creating **AlbumTitle** with type **String**.

![Write Data Dashboard!](/images/2-prerequisite/2.1.3-writedata/0004-writedata.png "WriteData")

8. Enter values ​​for items:

- **Artist**, enter **`No One You Know`**

- **SongTitle**, enter **`Call Me Today`**

- **AlbumTitle**, enter **`Somewhat Famous`**

- **Awards**, enter **`1`**.
  
![Write Data Dashboard!](/images/2-prerequisite/2.1.3-writedata/0005-writedata.png "WriteData")

9. Select **Create item**.

![Write Data Dashboard!](/images/2-prerequisite/2.1.3-writedata/0005-writedata.png "WriteData")

10. Repeat step 8 and create another entry with the following values:

- **Artist**, enter **`Acme Band`**.

- **SongTitle** enter **`Happy Day`**.

- **AlbumTitle**, enter **`Songs About Life`**.

- **Awards**, enter **`10`**.

![Write Data Dashboard!](/images/2-prerequisite/2.1.3-writedata/0006-writedata.png "WriteData")

11. Do this again to create another item with the same Artist as the previous step, but different values ​​for the other attributes:
- **Artist**, enter **`Acme Band`**.

- **SongTitle** import **`PartiQL Rocks`**.

- **AlbumTitle**, enter **`Another Album Title`**.

- **Awards**, enter **`8`**.

![Write Data Dashboard!](/images/2-prerequisite/2.1.3-writedata/0007-writedata.png "WriteData")

12. Result:

![Write Data Dashboard!](/images/2-prerequisite/2.1.3-writedata/0008-writedata.png "WriteData")