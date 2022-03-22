---
title : "Truy vấn Global secondary index"
date :  "`r Sys.Date()`" 
weight : 8
chapter : false
pre : " <b> 2.1.8 </b> "
---

1. Đăng nhập vào bảng điều khiển quản lý AWS và mở DynamoDB Console tại [Giao diện quản lý DynamoDB](https://console.aws.amazon.com/dynamodb/).
2. Trong thanh điều hướng ở bên trái của bảng điều khiển, chọn **Tables**
3. Chọn table **Music** từ danh sách table.
4. Chọn **Actions**, sau đó chọn **Explore item**.

![Query Global Secondary Index!](/images/2-prerequisite/2.1.8-querytheglobalsecondaryindex/0001-querytheglobalsecondaryindex.png "Query Global Secondary Index")

5. Chọn **Query**
6. Trong danh sách thả xuống bên dưới **Query**, chọn **AlbumTitle-index**
7. Đối với **AlbumTitle** , nhập **`Somewhat Famous`**, .
8. Chọn **Run**
9. Kết quả trả về: 
  
![Query Global Secondary Index!](/images/2-prerequisite/2.1.8-querytheglobalsecondaryindex/0002-querytheglobalsecondaryindex.png "Query Global Secondary Index")