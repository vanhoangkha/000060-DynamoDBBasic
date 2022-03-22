---
title : "Tạo Global secondary index"
date :  "`r Sys.Date()`" 
weight : 7
chapter : false
pre : " <b> 2.1.7 </b> "
---

1. Đăng nhập vào bảng điều khiển quản lý AWS và mở DynamoDB Console tại [Giao diện quản lý DynamoDB](https://console.aws.amazon.com/dynamodb/).

2. Trong thanh điều hướng ở bên trái của bảng điều khiển, chọn **Tables**

3. Chọn table **Music** từ danh sách table.

![Create Global Secondary Index!](/images/2-prerequisite/2.1.7-creategobalsecondaryindex/0001-creategobalsecondaryindex.png "Create Global Secondary Index")

4. Chọn tab **Indexes** từ table **Music**.

5. Chọn **Create index**
   
![Create Global Secondary Index!](/images/2-prerequisite/2.1.7-creategobalsecondaryindex/0002-creategobalsecondaryindex.png "Create Global Secondary Index")

6. Đối với **Partition key** , nhập **`AlbumTitle`**.

7. Đối với **Index name**, nhập **`AlbumTitle-index`**.

![Create Global Secondary Index!](/images/2-prerequisite/2.1.7-creategobalsecondaryindex/0003-creategobalsecondaryindex.png "Create Global Secondary Index")

8. Các item khác để mặc định và chọn **Create index**

![Create Global Secondary Index!](/images/2-prerequisite/2.1.7-creategobalsecondaryindex/0004-creategobalsecondaryindex.png "Create Global Secondary Index")

9. Kết quả:

![Create Global Secondary Index!](/images/2-prerequisite/2.1.7-creategobalsecondaryindex/0005-creategobalsecondaryindex.png "Create Global Secondary Index")
