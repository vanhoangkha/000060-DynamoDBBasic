---
title : "Truy vấn dữ liệu"
date :  "`r Sys.Date()`" 
weight : 6
chapter : false
pre : " <b> 2.1.6 </b> "
---

Các bước truy vấn dữ liệu bảng **Music** như sau:

1. Đăng nhập vào Bảng điều khiển quản lý AWS và mở DynamoDB Console tại [Giao diện quản lý DynamoDB](https://console.aws.amazon.com/dynamodb/).


2. Trong thanh điều hướng ở bên trái của bảng điều khiển, chọn **Tables**

3. Chọn bảng **Music** từ danh sách bảng.

4. Chọn **Actions**, sau đó chọn **Explore item**.
  
![Query Data  Dashboard!](/images/2-prerequisite/2.1.6-querydata/0001-querydata.png "UpdateData")

5. Chọn **Query**

6. Nhập chi tiết các key:

	- Đối với **Artist (Partition key)**, nhập **`Acme Band`**

	- Đối với **SongTitle (Sort key)**, nhập **`PartiQL Rocks`**

7. Chọn **Run**
8. Kết quả trả về: 

![Query Data  Dashboard!](/images/2-prerequisite/2.1.6-querydata/0002-querydata.png "UpdateData")
