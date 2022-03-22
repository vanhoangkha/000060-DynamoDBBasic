---
title : "Xóa dữ liệu table"
date : "`r Sys.Date()`"
weight : 9
chapter : false
pre : " <b> 3.2.9 </b> "
---

1. Tạo file có tên **`MoviesDeleteTable.py`**

2. Sao chép đoạn mã sau và dán vào file **`MoviesDeleteTable.py`**
```
import boto3


def delete_movie_table(dynamodb=None):
    dynamodb = boto3.resource('dynamodb')
    table = dynamodb.Table('Movies')
    table.delete()


if __name__ == '__main__':
    delete_movie_table()
    print("Movies table deleted.")
```
3. Chạy chương trình bằng **Window Command Prompt** đã được xác thực và cấu hình ở [bước 3.1 Cấu hình AWS CLI](../../3.1-configureawscli/). Gõ lệnh:

```
python MoviesDeleteTable.py
```
Trường hợp khác: sử dụng **`python "đường dẫn file MoviesDeleteTable.py"`**

4. Sau khi chạy chương trình, thu được kết quả

```
Movies table deleted.

```