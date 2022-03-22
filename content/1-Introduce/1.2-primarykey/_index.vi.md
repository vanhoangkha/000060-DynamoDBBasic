---
title : "Primary Key"
date :  "`r Sys.Date()`" 
weight : 2 
chapter : false
pre : " <b> 1.2 </b> "
---
{{% notice info %}}
Khi bạn tạo một table, ngoài tên table, bạn phải chỉ định **primary key** của table. 
{{% /notice %}}
- Primary key xác định duy nhất từng item trong table, do đó không có hai item nào có thể có cùng một key.
- DynamoDB hỗ trợ hai loại primary key khác nhau:
	+  **Partition key**
	+  **Composite primary key**
  
#### **Partition key**
- Một primary key đơn giản, bao gồm một attritube được gọi là **Partition key**.
- **DynamoDB** sử dụng giá trị của partition key làm đầu vào cho hàm băm bên trong. Đầu ra từ hàm băm xác định phân vùng (bộ nhớ vật lý bên trong DynamoDB) mà item sẽ được lưu trữ.
- Trong table chỉ có partition key, không có hai item nào có thể có cùng giá trị Partition key.

#### **Composite primary key**
- Attritube đầu tiên là **partition key** và attritube thứ hai là **sort key**.
- **DynamoDB** sử dụng giá trị partition key làm đầu vào cho hàm băm bên trong. Đầu ra từ hàm băm xác định phân vùng (bộ nhớ vật lý bên trong DynamoDB) mà item sẽ được lưu trữ.  
- Tất cả các item có cùng giá trị partition key được lưu trữ cùng nhau, theo thứ tự được sắp xếp theo giá trị sort key.
- Trong table có partition key và sort key, nhiều item có thể có cùng giá trị partition key. Tuy nhiên, các item đó phải có các giá trị sort key khác nhau.
- **Composite primary key** giúp bạn linh hoạt hơn khi truy vấn dữ liệu.
