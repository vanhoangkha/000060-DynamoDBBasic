---
title : "Write data"
date : "`r Sys.Date()`"
weight : 2
chapter : false
pre : " <b> 3.2.2 </b> "
---

Add items to the **Movies** table just created in [3.4.1-Create Table](3.4-pythonanddynamodb/../../3.4.1-createtable/)

1. Create a file named **`MoviesItemOps01.py`**

2. Copy the following program and paste it into the file **`MoviesItemOps01.py`**

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

3. Run the program using the authenticated and configured **Window Command Prompt** in [step 3.1 Configure AWS CLI](../../3.1-configureawscli/). Type command:

```
python MoviesItemOps01.py
```
Other case: use **`python "MoviesItemOps01.py file path"`**

4. After running the program, get the following results:

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