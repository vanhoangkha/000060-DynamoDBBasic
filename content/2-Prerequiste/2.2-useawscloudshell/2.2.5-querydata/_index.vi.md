---
title : "Truy vấn dữ liệu"
date : "`r Sys.Date()`"
weight : 5
chapter : false
pre : " <b> 2.2.5 </b> "
---

- Để truy vấn dữ liệu từ bảng, sử dụng lệnh **`query`** và cung cấp **partition key**.

1. Thực hiện lệnh:
  
```
aws dynamodb query \
    --table-name Music \
    --key-condition-expression "Artist = :name" \
    --expression-attribute-values  '{":name":{"S":"Acme Band"}}'
 ```

 2. Kết quả:

- Kết quả trên AWS CloudShell:

```
{
    "Items": [
        {
            "AlbumTitle": {
                "S": "Updated Album Title"
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
        },
        {
            "AlbumTitle": {
                "S": "Another Album Title"
            },
            "Awards": {
                "N": "8"
            },
            "Artist": {
                "S": "Acme Band"
            },
            "SongTitle": {
                "S": "PartiQL Rocks"
            }
        }
    ],
    "Count": 2,
    "ScannedCount": 2,
    "ConsumedCapacity": null
}
```

- Kết quả trên giao diện:

![Query Data CloudShell!](/images/2-prerequisite/2.2-usecloudshell/2.2.5-querydata/0001-querydata.png "Query Data CloudShell")