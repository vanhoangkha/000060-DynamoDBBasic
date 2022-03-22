---
title : " Đọc dữ liệu"
date :  "`r Sys.Date()`" 
weight : 4
chapter : false
pre : " <b> 2.1.4 </b> "
---

Các bước đọc dữ liệu từ table Music bằng DynamoDB console:

1. Đăng nhập vào bảng điều khiển quản lý AWS và mở DynamoDB Console tại [Giao diện quản lý DynamoDB](https://console.aws.amazon.com/dynamodb/).

2. Trong thanh điều hướng ở bên trái của bảng điều khiển, chọn **Tables**

3. Chọn table **Music** từ danh sách table.

4. Chọn **Actions**, sau đó chọn **Explore items**.
  
![Read Data  Dashboard!](/images/2-prerequisite/2.1.4-readdata/0001-readdata.png "ReadData")

5. Chọn **Query**, sau đó điền **Artist (Partition key)** là **`Acme Band`**
   
![Read Data  Dashboard!](/images/2-prerequisite/2.1.4-readdata/0002-readdata.png "ReadData")

6. Chọn **Run** và thu kết quả như hình:
  
![Read Data  Dashboard!](/images/2-prerequisite/2.1.4-readdata/0003-readdata.png "ReadData")


