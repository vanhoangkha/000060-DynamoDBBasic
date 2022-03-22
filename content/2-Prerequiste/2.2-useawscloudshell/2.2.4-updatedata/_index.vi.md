---
title : "Cập nhật dữ liệu"
date : "`r Sys.Date()`"
weight : 4
chapter : false
pre : " <b> 2.2.4 </b> "
---

- Để cập nhật dữ liệu, sử dụng lệnh **`update-item`**

1. Thực hiện lệnh:

```
aws dynamodb update-item \
    --table-name Music \
    --key '{ "Artist": {"S": "Acme Band"}, "SongTitle": {"S": "Happy Day"}}' \
    --update-expression "SET AlbumTitle = :newval" \
    --expression-attribute-values '{":newval":{"S":"Updated Album Title"}}' \
    --return-values ALL_NEW
 ```
2. Kết quả:

- Kết quả trên AWS CLoudShell:

```
{
    "Attributes": {
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
    }
}
```
-  Kết quả trên giao diện:


![Update Data CloudShell!](/images/2-prerequisite/2.2-usecloudshell/2.2.4-updatedata/0001-updatedata.png "Update Data CloudShell")