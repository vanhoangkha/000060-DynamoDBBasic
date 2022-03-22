---
title : "Xóa dữ liệu"
date : "`r Sys.Date()`"
weight : 5
chapter : false
pre : " <b> 3.4.5 </b> "
---

1. Tạo file có tên **`MoviesItemOps04.py`**

2. Sao chép đoạn mã sau và dán vào file **`MoviesItemOps04.py`**

```
from decimal import Decimal
from pprint import pprint
import boto3
from botocore.exceptions import ClientError


def delete_underrated_movie(title, year, rating, dynamodb=None):
    dynamodb = boto3.resource('dynamodb')
    table = dynamodb.Table('Movies')

    try:
        response = table.delete_item(
            Key={
                'year': year,
                'title': title
            }
        )
    except ClientError as e:
        if e.response['Error']['Code'] == "ConditionalCheckFailedException":
            print(e.response['Error']['Message'])
        else:
            raise
    else:
        return response


if __name__ == '__main__':
    print("Attempting a conditional delete...")
    delete_response = delete_underrated_movie("The Big New Movie", 2015, 5)
    if delete_response:
        print("Delete movie succeeded:")
        pprint(delete_response, sort_dicts=False)

```
1. Chạy chương trình bằng **Window Command Prompt** đã được xác thực và cấu hình ở [bước 3.1 Cấu hình AWS CLI](../../3.1-configureawscli/). Gõ lệnh:

```
python MoviesItemOps03.py
```
Trường hợp khác: sử dụng **`python "đường dẫn file MoviesItemOps03.py"`**

4. Sau khi chạy chương trình, thu được kết quả: 

```
Attempting a conditional delete...
Delete movie succeeded:
{'ResponseMetadata': {'RequestId': 'HHA9MQ2U0UP1CL7CECBAAQRMMVVV4KQNSO5AEMVJF66Q9ASUAAJG',
                      'HTTPStatusCode': 200,
                      'HTTPHeaders': {'server': 'Server',
                                      'date': 'Wed, 09 Feb 2022 03:39:32 GMT',
                                      'content-type': 'application/x-amz-json-1.0',
                                      'content-length': '2',
                                      'connection': 'keep-alive',
                                      'x-amzn-requestid': 'HHA9MQ2U0UP1CL7CECBAAQRMMVVV4KQNSO5AEMVJF66Q9ASUAAJG',
                                      'x-amz-crc32': '2745614147'},
                      'RetryAttempts': 0}}
```
