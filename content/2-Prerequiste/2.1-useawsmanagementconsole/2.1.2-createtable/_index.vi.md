---
title : "Tạo bảng"
date :  "`r Sys.Date()`" 
weight : 2
chapter : false
pre : " <b> 2.1.2 </b> "
---

Trong bước này, bạn tạo một bảng Music trong Amazon DynamoDB. Bảng có các chi tiết sau:

- **Partition key** — Artist

- **Sort key** — SongTitle

1. Đăng nhập vào Bảng điều khiển quản lý AWS và mở DynamoDB Console tại [Giao diện quản lý DynamoDB](https://console.aws.amazon.com/dynamodb/).

2. Trong thanh điều hướng ở bên trái của bảng điều khiển, chọn **Dashboard**.

3. Ở phía bên phải của bảng điều khiển, chọn **Create Table**.

![Create Table Dashboard!](/images/2-prerequisite/2.1.2-createtable/0001-createtable.png "CreateTableDashboard")

4. Nhập chi tiết bảng như sau:

- Đối với  **Table name**, hãy nhập **``` Music ```**.

- Đối với  **Partition key**, hãy nhập **```Artist```**.

- Nhập **SongTitle** làm **Sort key**.

- Chọn **Default settings**.
  
![Create Table Dashboard!](/images/2-prerequisite/2.1.2-createtable/0002-createtable.png "CreateTableDashboard")

5. Chọn **Create table** để tạo bảng.

![Create Table Dashboard!](/images/2-prerequisite/2.1.2-createtable/0003-createtable.png "CreateTableDashboard")


