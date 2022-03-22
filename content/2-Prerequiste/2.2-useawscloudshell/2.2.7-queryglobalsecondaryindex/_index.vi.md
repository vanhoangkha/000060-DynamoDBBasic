---
title : "Truy vấn Global secondary index"
date : "`r Sys.Date()`"
weight : 7
chapter : false
pre : " <b> 2.2.7 </b> "
---

- Để truy vấn Global Secondary Index, sử dụng lệnh `query`

1. Thực hiện lệnh:
  
```
aws dynamodb query \
    --table-name Music \
    --index-name AlbumTitle-index \
    --key-condition-expression "AlbumTitle = :name" \
    --expression-attribute-values  '{":name":{"S":"Somewhat Famous"}}'
 ```

 2. Kết quả:

- Kết quả trên AWS CloudShell:

```
{
    "Items": [
        {
            "AlbumTitle": {
                "S": "Somewhat Famous"
            },
            "Awards": {
                "N": "1"
            },
            "Artist": {
                "S": "No One You Know"
            },
            "SongTitle": {
                "S": "Call Me Today"
            }
        },
        {
            "AlbumTitle": {
                "S": "Somewhat Famous"
            },
            "Awards": {
                "N": "2"
            },
            "Artist": {
                "S": "No One You Know"
            },
            "SongTitle": {
                "S": "Howdy"
            }
        }
    ],
    "Count": 2,
    "ScannedCount": 2,
    "ConsumedCapacity": null
}

```
- Kết quả trên giao diện:

![Query Gobal Secondary Index CloudShell!](/images/2-prerequisite/2.2-usecloudshell/2.2.7-querygobalsecondaryindex/0001-querygobalsecondaryindexsecondary.png " Query Gobal Secondary Index CloudShell")