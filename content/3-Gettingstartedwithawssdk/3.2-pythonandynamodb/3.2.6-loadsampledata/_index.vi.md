---
title : "Tải dữ liệu mẫu"
date : "`r Sys.Date()`"
weight : 6
chapter : false
pre : " <b> 3.2.6 </b> "
---

1. Tải xuống dữ liệu mẫu.

{{%attachments style="orange" title="MovieData" pattern=".*(zip)"/%}}

2. Giải nén tệp dữ liệu (**moviedata.json**) từ kho lưu trữ.

3. Sao chép tệp **moviedata.json** vào thư item hiện tại của bạn.

4. Tạo file có tên **`MoviesLoadData.py`**

5. Sao chép đoạn mã sau và dán vào file **`MoviesLoadData.py`**

```
from decimal import Decimal
import json
import boto3


def load_movies(movies, dynamodb=None):
    dynamodb = boto3.resource('dynamodb')
    table = dynamodb.Table('Movies')
    for movie in movies:
        year = int(movie['year'])
        title = movie['title']
        print("Adding movie:", year, title)
        table.put_item(Item=movie)


if __name__ == '__main__':
    with open("moviedata.json") as json_file:
        movie_list = json.load(json_file, parse_float=Decimal)
    load_movies(movie_list)

```
6. Chạy chương trình bằng **Window Command Prompt** đã được xác thực và cấu hình ở [bước 3.1 Cấu hình AWS CLI](../../3.1-configureawscli/). Gõ lệnh:

```
python MoviesLoadData.py
```
Trường hợp khác: sử dụng **`python "đường dẫn file MoviesLoadData.py"`**

7. Sau khi chạy chương trình, thu được kết quả: 
```
Adding movie: 2013 Insidious: Chapter 2
Adding movie: 2013 World War Z
Adding movie: 2014 X-Men: Days of Future Past
Adding movie: 2014 Transformers: Age of Extinction
Adding movie: 2013 Now You See Me
Adding movie: 2013 Gravity
Adding movie: 2013 We're the Millers
Adding movie: 2013 Riddick
Adding movie: 2013 The Family
Adding movie: 2013 Star Trek Into Darkness
Adding movie: 2013 After Earth
Adding movie: 2013 The Great Gatsby
Adding movie: 2014 Divergent
Adding movie: 2013 We Are What We Are
Adding movie: 2013 Iron Man 3
Adding movie: 2014 The Amazing Spider-Man 2
Adding movie: 2013 Curse of Chucky
Adding movie: 2013 The Conjuring
Adding movie: 2013 Oldboy
Adding movie: 2013 Escape Plan
Adding movie: 2013 Elysium
Adding movie: 2013 Cloudy with a 
```
Lưu ý: Đúng đường dẫn file **`moviedata.json`**
