---
title : "Tạo bảng"
date : "`r Sys.Date()`"
weight : 1
chapter : false
pre : " <b> 3.2.1 </b> "
---

Trong bước này, chúng ta tạo một bảng có tên **Movies**. primary key cho bảng bao gồm các thuộc tính sau:

**year** – The partition key. AttributeType là N(number).

**title** – The sort key. AttributeType là S(string).

1. Tạo file có tên **`MoviesCreateTable.py`**

2. Sao chép đoạn mã sau và dán vào file **`MoviesCreateTable.py`**

```
import boto3


def create_movie_table(dynamodb=None):
    dynamodb = boto3.resource('dynamodb')
    table = dynamodb.create_table(
        TableName='Movies',
        KeySchema=[
            {
                'AttributeName': 'year',
                'KeyType': 'HASH'  # Partition key
            },
            {
                'AttributeName': 'title',
                'KeyType': 'RANGE'  # Sort key
            }
        ],
        AttributeDefinitions=[
            {
                'AttributeName': 'year',
                'AttributeType': 'N'
            },
            {
                'AttributeName': 'title',
                'AttributeType': 'S'
            },

        ],
        ProvisionedThroughput={
            'ReadCapacityUnits': 10,
            'WriteCapacityUnits': 10
        }
    )
    return table


if __name__ == '__main__':
    movie_table = create_movie_table()
    print("Table status:", movie_table.table_status)

```

3. Chạy chương trình bằng **Window Command Prompt** đã được xác thực và cấu hình ở [bước 3.1 Cấu hình AWS CLI](../../3.1-configureawscli/). Gõ lệnh:
  
```
python MoviesCreateTable.py
```
Trường hợp khác: sử dụng **`python "đường dẫn file MoviesCreateTable.py"`**

4. Sau khi chạy chương trình trả về **`Table status: CREATING`** là tạo bảng thành công.