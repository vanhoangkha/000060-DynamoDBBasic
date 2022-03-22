---
title : "Read data"
date : "`r Sys.Date()`"
weight : 3
chapter : false
pre : " <b> 3.2.3 </b> "
---

1. Create a file named **`MoviesItemOps02.py`**

2. Copy the following code and paste it in **`MoviesItemOps02.py`**

```
from pprint import pprint
import boto3
from botocore.exceptions import ClientError


def get_movie(title, year, dynamodb=None):
    dynamodb = boto3.resource('dynamodb')
    table = dynamodb.Table('Movies')

    try:
        response = table.get_item(Key={'year': year, 'title': title})
    except ClientError as e:
        print(e.response['Error']['Message'])
    else:
        return response['Item']


if __name__ == '__main__':
    movie = get_movie("The Big New Movie", 2015,)
    if movie:
        print("Get movie succeeded:")
        pprint(movie, sort_dicts=False)

```
3. Run the program using the authenticated and configured **Window Command Prompt** in [step 3.1 Configure AWS CLI](../../3.1-configureawscli/). Type command:

```
python MoviesItemOps02.py
```
Other case: use `python "MoviesItemOps02.py file path"`

4. After running the program, get the following results:

```
Get movie succeeded:
{'year': Decimal('2015'),
 'info': {'rating': Decimal('0'), 'plot': 'Nothing happens at all.'},
 'title': 'The Big New Movie'}
```