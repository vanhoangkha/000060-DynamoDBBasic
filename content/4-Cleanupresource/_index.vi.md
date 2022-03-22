---
title : "Dọn dẹp tài nguyên"
date :  "`r Sys.Date()`" 
weight : 4
chapter : false
pre : " <b> 4. </b> "
---

### Sử dụng AWS Management Console

  1. Mở table DynamoDB console tại  https://console.aws.amazon.com/dynamodb/

  2. Trong thanh điều hướng ở bên trái của bảng điều khiển, chọn **Tables**

  3. Chọn table **Music** từ danh sách table.

  4. Chọn **Actions**, sau đó chọn **Delete table**.



![Delete Table!](/images/2-prerequisite/4.cleanupresource/0001-cleanup.png "Delete Table")


### Sử dụng AWS CloudShell

- Để xóa table, sử dụng lệnh **`delete-table`**

- Gõ lệnh:
  
```
aws dynamodb delete-table --table-name Music
```
