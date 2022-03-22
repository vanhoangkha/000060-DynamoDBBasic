---
title : "Các thành phần cốt lõi của Amazon DynamoDB"
date :  "`r Sys.Date()`" 
weight : 1 
chapter : false
pre : " <b> 1.1 </b> "
---

- **Table**: Tương tự như các hệ thống cơ sở dữ liệu khác, DynamoDB lưu trữ dữ liệu trong table. Table là một tập hợp dữ liệu.

- **Item**: Mỗi table chứa không hoặc nhiều item. Các item trong DynamoDB khá tương đồng với khái niệm hàng trong cơ sở dữ liệu quan hệ, bản ghi hoặc bộ dữ liệu trong các hệ thống cơ sở dữ liệu khác. Trong DynamoDB, không có giới hạn về số lượng item bạn có thể lưu trữ trong một table.

- **Attribute**: Mỗi item bao gồm một hoặc nhiều attribute. Attribute là một phần tử dữ liệu cơ bản, không cần phải chia nhỏ thêm nữa. Các attribute trong DynamoDB theo nhiều cách tương tự với các cột trong các hệ thống cơ sở dữ liệu khác.