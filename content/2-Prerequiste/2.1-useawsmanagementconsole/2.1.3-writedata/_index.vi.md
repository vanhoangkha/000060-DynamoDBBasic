---
title : "Ghi dữ liệu"
date :  "`r Sys.Date()`" 
weight : 3 
chapter : false
pre : " <b> 2.1.3 </b> "
---

Các bước ghi dữ liệu vào table Music(đã tạo ở 2.1.2):

1. Đăng nhập vào bảng điều khiển quản lý AWS và mở DynamoDB Console tại [Giao diện quản lý DynamoDB](https://console.aws.amazon.com/dynamodb/).

2. Trong thanh điều hướng ở bên trái của bảng điều khiển, chọn **Tables**.

3. Trong danh sách table, hãy chọn table **Music**.
   
4. Chọn **Explore items**

![Write Data  Dashboard!](/images/2-prerequisite/2.1.3-writedata/0001-writedata.png "WriteData")

5. Trong giao diện **Items**, chọn **Create item**

![Write Data  Dashboard!](/images/2-prerequisite/2.1.3-writedata/0002-writedata.png "WriteData")

6. Chọn **Add new attribute**, sau đó chọn **Number**. Tên trường: **Awards**.

![Write Data  Dashboard!](/images/2-prerequisite/2.1.3-writedata/0003-writedata.png "WriteData")

7. Lặp lại bước 6 tạo **AlbumTitle** với kiểu **String**.

![Write Data  Dashboard!](/images/2-prerequisite/2.1.3-writedata/0004-writedata.png "WriteData")

8. Nhập các giá trị cho các item:

	- **Artist**, nhập **`No One You Know`**

	- **SongTitle**, nhập **`Call Me Today`**

	- **AlbumTitle**, nhập **`Somewhat Famous`**

	- **Awards**, nhập **`1`**.
  
![Write Data  Dashboard!](/images/2-prerequisite/2.1.3-writedata/0005-writedata.png "WriteData")

9. Chọn **Create item**.

![Write Data  Dashboard!](/images/2-prerequisite/2.1.3-writedata/0005-writedata.png "WriteData")

10.  Lặp lại bước 8 và tạo một item khác với các giá trị sau:

- **Artist**, nhập **`Acme Band`**.

- **SongTitle** nhập **`Happy Day`**.

- **AlbumTitle**, nhập **`Songs About Life`**.

- **Awards**, nhập **`10`**.

![Write Data  Dashboard!](/images/2-prerequisite/2.1.3-writedata/0006-writedata.png "WriteData")

11.  Thực hiện thao tác này một lần nữa để tạo một item khác có cùng một Artist như bước trước, nhưng các giá trị khác nhau cho các attritube khác:
- **Artist**, nhập **`Acme Band`**.

- **SongTitle** nhập **`PartiQL Rocks`**.

- **AlbumTitle**, nhập **`Another Album Title`**.

- **Awards**, nhập **`8`**.

![Write Data  Dashboard!](/images/2-prerequisite/2.1.3-writedata/0007-writedata.png "WriteData")

12.  Kết quả: 

![Write Data  Dashboard!](/images/2-prerequisite/2.1.3-writedata/0008-writedata.png "WriteData")
