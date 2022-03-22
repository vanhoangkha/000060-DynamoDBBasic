---
title : "Quy tắc đặt tên và kiểu dữ liệu"
date :  "`r Sys.Date()`" 
weight : 4
chapter : false
pre : " <b> 1.4</b> "
---

#### **Quy tắc đặt tên**
- Các bảng, thuộc tính và các đối tượng khác trong **DynamoDB** phải có tên.
- Sau đây là các quy tắc đặt tên cho DynamoDB:
	+ Tất cả các tên phải được mã hóa bằng ***UTF-8*** và có ***phân biệt chữ hoa chữ thường***.
	+ Tên bảng và tên chỉ mục phải dài từ ***3 đến 255 ký tự*** và chỉ được chứa các ký tự sau:
		- a-z
		- A-Z
		- 0-9
		- _(gạch dưới)
		- -(gạch ngang)
		- . (dấu chấm)
- Tên thuộc tính phải dài ít nhất một ký tự, nhưng không dài hơn 64 KB.
- Sau đây là các trường hợp ngoại lệ. Các tên thuộc tính này không được dài quá 255 ký tự:
	+ Tên khóa của phân vùng Secondary Index.
	+ Secondary Index sắp xếp các tên khóa.
	+ Tên của bất kỳ thuộc tính dự kiến ​​nào do người dùng chỉ định (chỉ áp dụng cho các Secondary Index cục bộ).
  
#### **Kiểu dữ liệu**
**DynamoDB** hỗ trợ nhiều kiểu dữ liệu khác nhau cho các thuộc tính trong bảng. Chúng có thể được phân loại như sau:
- **Các kiểu vô hướng:** Một kiểu vô hướng có thể biểu diễn chính xác một giá trị. Các kiểu vô hướng là **số, chuỗi, nhị phân, Boolean và null**.
- **Loại tài liệu:** Một loại tài liệu có thể đại diện cho một cấu trúc phức tạp với các thuộc tính lồng nhau, chẳng hạn như bạn sẽ tìm thấy trong tài liệu JSON. Các loại tài liệu là **list** và **map**.
- **Loại tập hợp:** Một loại tập hợp có thể đại diện cho nhiều giá trị vô hướng. Các loại tập hợp là **tập hợp chuỗi, tập hợp số và tập hợp nhị phân**.