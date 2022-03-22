---
title : "Cập nhật dữ liệu"
date :  "`r Sys.Date()`" 
weight : 5
chapter : false
pre : " <b> 2.1.5 </b> "
---

Các bước cập nhật dữ liệu bảng Music như sau:

1. Đăng nhập vào Bảng điều khiển quản lý AWS và mở DynamoDB Console tại [Giao diện quản lý DynamoDB](https://console.aws.amazon.com/dynamodb/).

2. Trong thanh điều hướng ở bên trái của bảng điều khiển, chọn **Tables**

3. Chọn bảng **Music** từ danh sách bảng.

4. Chọn **Actions**, sau đó chọn **Explore item**.

![Update Data  Dashboard!](/images/2-prerequisite/2.1.5-updatedata/0001-updatedata.png "UpdateData")

5. Chọn item có giá trị **Artist** là **`Acme Band`** và giá trị **SongTitle** là **`Happy Day`**.

![Update Data  Dashboard!](/images/2-prerequisite/2.1.5-updatedata/0002-updatedata.png "UpdateData")

6. Cập nhật giá trị **Album Title** thành **Updated Album Title**, sau đó chọn **Save changes**.

![Update Data  Dashboard!](/images/2-prerequisite/2.1.5-updatedata/0003-updatedata.png "UpdateData")

7. Kết quả sau khi cập nhật dữ liệu:

![Read Data  Dashboard!](/images/2-prerequisite/2.1.5-updatedata/0004-updatedata.png "ReadData")