---
title : "Cập nhật dữ liệu"
date : "`r Sys.Date()`"
weight : 4
chapter : false
pre : " <b> 3.2.4 </b> "
---

1. Tạo file có tên **`MoviesItemOps03.py`**

2. Sao chép đoạn mã sau và dán vào file **`MoviesItemOps03.py`**

```
from decimal import Decimal
from pprint import pprint
import boto3


def update_movie(title, year, rating, plot, actors, dynamodb=None):
    dynamodb = boto3.resource('dynamodb')
    table = dynamodb.Table('Movies')

    response = table.update_item(
        Key={
            'year': year,
            'title': title
        },
        UpdateExpression="set info.rating=:r, info.plot=:p, info.actors=:a",
        ExpressionAttributeValues={
            ':r': Decimal(rating),
            ':p': plot,
            ':a': actors
        },
        ReturnValues="UPDATED_NEW"
    )
    return response


if __name__ == '__main__':
    update_response = update_movie(
        "The Big New Movie", 2015, 5.5, "Everything happens all at once.",
        ["Larry", "Moe", "Curly"])
    print("Update movie succeeded:")
    pprint(update_response, sort_dicts=False)

```

3. Chạy chương trình bằng **Window Command Prompt** đã được xác thực và cấu hình ở [bước 3.1 Cấu hình AWS CLI](../../3.1-configureawscli/). Gõ lệnh:

```
python MoviesItemOps03.py
```
Trường hợp khác: sử dụng **`python "đường dẫn file MoviesItemOps03.py"`**

4. Sau khi chạy chương trình, thu được kết quả:

```
Update movie succeeded:
{'Attributes': {'info': {'actors': ['Larry', 'Moe', 'Curly'],
                         'plot': 'Everything happens all at once.',
                         'rating': Decimal('5.5')}},
 'ResponseMetadata': {'RequestId': 'RFMTVB72A6E2J39HBPIK8SHBN7VV4KQNSO5AEMVJF66Q9ASUAAJG',
                      'HTTPStatusCode': 200,
                      'HTTPHeaders': {'server': 'Server',
                                      'date': 'Wed, 09 Feb 2022 03:29:15 GMT',
                                      'content-type': 'application/x-amz-json-1.0',
                                      'content-length': '156',
                                      'connection': 'keep-alive',
                                      'x-amzn-requestid': 'RFMTVB72A6E2J39HBPIK8SHBN7VV4KQNSO5AEMVJF66Q9ASUAAJG',
                                      'x-amz-crc32': '3767510606'},
                      'RetryAttempts': 0}}

```
