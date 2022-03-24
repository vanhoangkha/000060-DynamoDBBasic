---
title : "Secondary Index"
date :  "`r Sys.Date()`" 
weight : 3 
chapter : false
pre : " <b> 1.3 </b> "
---

- Bạn có thể tạo một hoặc nhiều **Secondary Index** trên một table. 
- Secondary Index cho phép truy vấn dữ liệu trong table bằng các key khác với partition key và sort ban đầu của table. Với Dynamo DB thao tác query dữ liệu có tốc độ nhanh và tiết kiệm chi phí hơn rất nhiều so với thao tác scan.

Dưới đây là DynamoDB table ví dụ:

![Query](/images/1-introduce/1.4-namingrulesanddatatypes/0001-Diagram-Base-Table.png)

- Nếu thực hiện thao tác query dữ liệu chúng ta có thể tìm dữ liệu theo giá trị Partition Key và Sort Key.

![Query](/images/1-introduce/1.5-readconsistency/0001-Diagram-Query.png)

- Nếu thực hiện thao tác scan dữ liệu, chúng ta sẽ scan toàn bộ bảng sau đó thực hiện filter theo một attribute bất kỳ. ( Khi thực hiện filter thực chất chúng ta vẫn phải tốn chi phí scan toàn bộ bảng.)

![Scan](/images/1-introduce/1.6-readwritecapacitymode/0001-Diagram-Scan.png)

- DynamoDB không bắt buộc bạn phải sử dụng  index, nhưng chúng giúp các ứng dụng của bạn linh hoạt hơn khi query dữ liệu. Sau khi tạo Secondary Index trên table, bạn có thể đọc dữ liệu từ index theo cách giống như đọc dữ liệu từ table.


DynamoDB hỗ trợ hai loại index:

- **Global secondary index** index có partition key và sort key có thể khác với các index trên table.

![Secondary Index](/images/1-introduce/1.3-secondaryindexes/0002-Diagram-Global-Secondary-Indexs.png)

- **Local secondary index**  index có cùng partition key với table nhưng có sort key khác.

![Secondary Index](/images/1-introduce/1.3-secondaryindexes/0001-Diagram-Local-Secondary-Indexs.png)

{{% notice tip %}}
Mỗi table trong DynamoDB có tối đa **20 Global secondary index** (giới hạn mặc định) và **5 Local secondary index**.
{{% /notice %}}