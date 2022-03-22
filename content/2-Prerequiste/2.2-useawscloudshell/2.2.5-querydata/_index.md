---
title : "Query data"
date : "`r Sys.Date()`"
weight : 5
chapter : false
pre : " <b> 2.2.5 </b> "
---

- To query data from table, use **`query`** command and provide **partition key**.

1. Execute the command:
  
```
aws dynamodb query \
    --table-name Music \
    --key-condition-expression "Artist = :name" \
    --expression-attribute-values ​​'{":name":{"S":"Acme Band"}}'
 ```

 2. Result:

- Results on AWS CloudShell:

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

- Result on the interface:

![Query Data CloudShell!](/images/2-prerequisite/2.2-usecloudshell/2.2.5-querydata/0001-querydata.png "Query Data CloudShell")