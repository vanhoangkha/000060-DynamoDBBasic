---
title : "Đọc dữ liệu"
date : "`r Sys.Date()`"
weight : 3
chapter : false
pre : " <b> 3.2.3 </b> "
---

1. Tạo file có tên **`MoviesItemOps02.py`**

2. Sao chép đoạn mã sau và dán vào file **`MoviesItemOps02.py`**

```
from pprint import pprint
import boto3
from botocore.exceptions import ClientError


def get_movie(title, year, dynamodb=None):
    dynamodb = boto3.resource('dynamodb')
    table = dynamodb.Table('Movies')

    try:
        response = table.get_item(Key={'year': year, 'title': title})
    except ClientError as e:
        print(e.response['Error']['Message'])
    else:
        return response['Item']


if __name__ == '__main__':
    movie = get_movie("The Big New Movie", 2015,)
    if movie:
        print("Get movie succeeded:")
        pprint(movie, sort_dicts=False)

```
3. Chạy chương trình bằng **Window Command Prompt** đã được xác thực và cấu hình ở [bước 3.1 Cấu hình AWS CLI](../../3.1-configureawscli/). Gõ lệnh:

```
python MoviesItemOps02.py
```
Trường hợp khác: sử dụng `python "đường dẫn file MoviesItemOps02.py"`

4. Sau khi chạy chương trình, thu được kết quả:

```
Get movie succeeded:
{'year': Decimal('2015'),
 'info': {'rating': Decimal('0'), 'plot': 'Nothing happens at all.'},
 'title': 'The Big New Movie'}
```
