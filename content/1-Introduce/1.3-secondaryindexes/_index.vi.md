---
title : "Secondary Index"
date :  "`r Sys.Date()`" 
weight : 3 
chapter : false
pre : " <b> 1.3 </b> "
---
{{% notice note %}} 
Bạn có thể tạo một hoặc nhiều **Secondary Index** trên một table. 
{{% /notice %}}

![Secondary Index](/images/1-introduce/1.3-secondaryindexes/0001-Diagram-Local-Secondary-Indexs.png)
- Secondary Index cho phép truy vấn dữ liệu trong table bằng các key khác với partition key và sort ban đầu của table. Với Dynamo DB thao tác query dữ liệu có tốc độ nhanh và tiết kiệm chi phí hơn rất nhiều so với thao tác scan.

- DynamoDB không bắt buộc bạn phải sử dụng  index, nhưng chúng giúp các ứng dụng của bạn linh hoạt hơn khi query dữ liệu. Sau khi tạo Secondary Index trên table, bạn có thể đọc dữ liệu từ index theo cách giống như đọc dữ liệu từ table.

![Secondary Index](/images/1-introduce/1.3-secondaryindexes/0002-Diagram-Global-Secondary-Indexs.png)
- DynamoDB hỗ trợ hai loại index:

	- **Global secondary index** index có partition key và sort key có thể khác với các index trên table.
	- **Local secondary index**  index có cùng partition key với table nhưng có sort key khác.

{{% notice tip %}}
Mỗi table trong DynamoDB có tối đa **20 Global secondary index** (giới hạn mặc định) và **5 Local secondary index**.
{{% /notice %}}