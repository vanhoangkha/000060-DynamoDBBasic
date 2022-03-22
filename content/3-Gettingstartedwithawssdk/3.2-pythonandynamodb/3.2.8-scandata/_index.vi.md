---
title : "Quét dữ liệu"
date : "`r Sys.Date()`"
weight : 8
chapter : false
pre : " <b> 3.2.8 </b> "
---

Phương thức **scan** đọc mọi item trong toàn bộ bảng và trả về tất cả dữ liệu trong bảng. Bạn có thể cung cấp một tùy chọn **filter_expression** để chỉ những mặt hàng phù hợp với tiêu chí của bạn mới được trả lại. Tuy nhiên, bộ lọc chỉ được áp dụng sau khi toàn bộ bảng đã được quét.

Chương trình sau quét toàn bộ bảng Movies, trong đó có khoảng 5.000 mục. Quá trình quét chỉ định bộ lọc tùy chọn để chỉ lấy các phim từ những năm 1950 (khoảng 100 mục) và loại bỏ tất cả các phim khác.

1. Tạo file có tên **`MoviesScan.py`**

2. Sao chép đoạn mã sau và dán vào file **`MoviesScan.py`**

```
from pprint import pprint
import boto3
from boto3.dynamodb.conditions import Key


def scan_movies(year_range, display_movies, dynamodb=None):
    dynamodb = boto3.resource('dynamodb')

    table = dynamodb.Table('Movies')
    scan_kwargs = {
        'FilterExpression': Key('year').between(*year_range),
        'ProjectionExpression': "#yr, title, info.rating",
        'ExpressionAttributeNames': {"#yr": "year"}
    }

    done = False
    start_key = None
    while not done:
        if start_key:
            scan_kwargs['ExclusiveStartKey'] = start_key
        response = table.scan(**scan_kwargs)
        display_movies(response.get('Items', []))
        start_key = response.get('LastEvaluatedKey', None)
        done = start_key is None


if __name__ == '__main__':
    def print_movies(movies):
        for movie in movies:
            print(f"\n{movie['year']} : {movie['title']}")
            pprint(movie['info'])

    query_range = (1950, 1959)
    print(
        f"Scanning for movies released from {query_range[0]} to {query_range[1]}...")
    scan_movies(query_range, print_movies)
```
Chú thích:

**ProjectionExpression** chỉ định các thuộc tính bạn muốn trong kết quả quét.

**FilterExpression** chỉ định một điều kiện chỉ trả về các mục thỏa mãn điều kiện. Tất cả các mục khác đều bị loại bỏ.

3. Chạy chương trình bằng **Window Command Prompt** đã được xác thực và cấu hình ở [bước 3.1 Cấu hình AWS CLI](../../3.1-configureawscli/). Gõ lệnh:

```
python MoviesScan.py
```
Trường hợp khác: sử dụng **`python "đường dẫn file MoviesScan.py"`**

4. Sau khi chạy chương trình, thu được kết quả

```

1958 : Cat on a Hot Tin Roof
{'rating': Decimal('8')}

1958 : Monster on the Campus
{'rating': Decimal('5.7')}

1958 : No Time for Sergeants
{'rating': Decimal('7.5')}

1958 : Teacher's Pet
{'rating': Decimal('7')}

1958 : Touch of Evil
{'rating': Decimal('8.2')}

1958 : Vertigo
{'rating': Decimal('8.5')}

1951 : A Streetcar Named Desire
{'rating': Decimal('8')}

1951 : Alice in Wonderland
{'rating': Decimal('7.4')}

1951 : An American in Paris
{'rating': Decimal('7.2')}

1951 : Operation Pacific
{'rating': Decimal('6.5')}

1951 : Storm Warning
{'rating': Decimal('7')}

1951 : Strangers on a Train
{'rating': Decimal('8.2')}

1951 : The African Queen
{'rating': Decimal('8')}

```
