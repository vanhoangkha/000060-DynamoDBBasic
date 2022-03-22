---
title : "Query Global Secondary Index"
date : "`r Sys.Date()`"
weight : 7
chapter : false
pre : " <b> 2.2.7 </b> "
---

- To query the Global Secondary Index, use the command `query`

1. Execute the command:
  
```
aws dynamodb query \
    --table-name Music \
    --index-name AlbumTitle-index \
    --key-condition-expression "AlbumTitle = :name" \
    --expression-attribute-values ​​'{":name":{"S":"Somewhat Famous"}}'
 ```

 2. Result:

- Results on AWS CloudShell:

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
- Result on the interface:

![Query Gobal Secondary Index CloudShell!](/images/2-prerequisite/2.2-usecloudshell/2.2.7-querygobalsecondaryindex/0001-querygobalsecondaryindexsecondary.png " Query Gobal Secondary Index CloudShell")
