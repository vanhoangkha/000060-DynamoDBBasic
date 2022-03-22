---
title : "Ghi dữ liệu"
date : "`r Sys.Date()`"
weight : 2
chapter : false
pre : " <b> 3.2.2 </b> "
---

Thực hiện thêm item vào bảng **Movies** vừa tạo ở [3.4.1-Tạo bảng](3.4-pythonanddynamodb/../../3.4.1-createtable/)

1. Tạo file có tên **`MoviesItemOps01.py`** 

2. Sao chép chương trình sau và dán vào file **`MoviesItemOps01.py`**

```
from pprint import pprint
import boto3


def put_movie(title, year, plot, rating, dynamodb=None):
    dynamodb = boto3.resource('dynamodb')
    table = dynamodb.Table('Movies')
    response = table.put_item(
        Item={
            'year': year,
            'title': title,
            'info': {
                'plot': plot,
                'rating': rating
            }
        }
    )
    return response


if __name__ == '__main__':
    movie_resp = put_movie("The Big New Movie", 2015,
                           "Nothing happens at all.", 0)
    print("Put movie succeeded:")
    pprint(movie_resp, sort_dicts=False)

```

3. Chạy chương trình bằng **Window Command Prompt** đã được xác thực và cấu hình ở [bước 3.1 Cấu hình AWS CLI](../../3.1-configureawscli/). Gõ lệnh:

```
python MoviesItemOps01.py
```
Trường hợp khác: sử dụng **`python "đường dẫn file MoviesItemOps01.py"`**

4. Sau khi chạy chương trình, thu được kết quả:

```
Put movie succeeded:
{'ResponseMetadata': {'RequestId': 'U9PQSVRR5PKKDD7NPV0NH91JD7VV4KQNSO5AEMVJF66Q9ASUAAJG',
                      'HTTPStatusCode': 200,
                      'HTTPHeaders': {'server': 'Server',
                                      'date': 'Wed, 09 Feb 2022 03:11:45 GMT',
                                      'content-type': 'application/x-amz-json-1.0',
                                      'content-length': '2',
                                      'connection': 'keep-alive',
                                      'x-amzn-requestid': 'U9PQSVRR5PKKDD7NPV0NH91JD7VV4KQNSO5AEMVJF66Q9ASUAAJG',
                                      'x-amz-crc32': '2745614147'},
                      'RetryAttempts': 0}}

```
