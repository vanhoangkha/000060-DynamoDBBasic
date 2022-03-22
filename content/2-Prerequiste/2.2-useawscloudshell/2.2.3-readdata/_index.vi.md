---
title : "Đọc dữ liệu"
date : "`r Sys.Date()`"
weight : 3
chapter : false
pre : " <b> 2.2.3 </b> "
---

- Để đọc dữ liệu, sử dụng lệnh **`get-item`** và tham số **`**consistent-read`** thể hiện **strongly consistent reads**.

- Mặc định của AWS DynamoDB là **eventually consistent reads**.

1. Thực hiện lệnh:
  
```
aws dynamodb get-item --consistent-read \
    --table-name Music \
    --key '{ "Artist": {"S": "Acme Band"}, "SongTitle": {"S": "Happy Day"}}'
```

2. Kết quả:
   
- Kết quả trên AWS CloudShell:
  
```
{
    "Item": {
        "AlbumTitle": {
            "S": "Songs About Life"
        },
        "Awards": {
            "N": "10"
        },
        "Artist": {
            "S": "Acme Band"
        },
        "SongTitle": {
            "S": "Happy Day"
        }
    }
}
```