---
title : "Read data"
date : "`r Sys.Date()`"
weight : 3
chapter : false
pre : " <b> 2.2.3 </b> "
---

- To read data, use the **`get-item`** command and the **`**consistent-read`** parameter represents **strongly consistent reads**.

- The default of AWS DynamoDB is **eventually consistent reads**.

1. Execute the command:
  
```
aws dynamodb get-item --consistent-read \
     --table-name Music \
     --key '{ "Artist": {"S": "Acme Band"}, "SongTitle": {"S": "Happy Day"}}'
```

2. Result:
   
- Results on AWS CloudShell:
  
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