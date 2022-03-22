---
title : "Scan data"
date : "`r Sys.Date()`"
weight : 8
chapter : false
pre : " <b> 3.2.8 </b> "
---

The **scan** method reads every item in the entire table and returns all the data in the table. You can provide a **filter_expression** option so that only items that match your criteria will be returned. However, the filter is only applied after the entire table has been scanned.

The following program scans the entire Movies table, which contains about 5,000 items. The scan specifies an optional filter to take only movies from the 1950s (about 100 items) and discard all other movies.

1. Create a file named **`MoviesScan.py`**

2. Copy the following code and paste it into the file **`MoviesScan.py`**

```
from pprint import pprint
import boto3
from boto3.dynamodb.conditions import Key


def scan_movies(year_range, display_movies, dynamodb=None):
    dynamodb = boto3.resource('dynamodb')

    table = dynamodb.Table('Movies')
    scan_kwargs = {
        'FilterExpression': Key('year').between(*year_range),
        'ProjectionExpression': "#yr, title, info.rating",
        'ExpressionAttributeNames': {"#yr": "year"}
    }

    done = False
    start_key = None
    while not done:
        if start_key:
            scan_kwargs['ExclusiveStartKey'] = start_key
        response = table.scan(**scan_kwargs)
        display_movies(response.get('Items', []))
        start_key = response.get('LastEvaluatedKey', None)
        done = start_key is None


if __name__ == '__main__':
    def print_movies(movies):
        for movie in movies:
            print(f"\n{movie['year']} : {movie['title']}")
            pprint(movie['info'])

    query_range = (1950, 1959)
    print(
        f"Scanning for movies released from {query_range[0]} to {query_range[1]}...")
    scan_movies(query_range, print_movies)
```
Note:

**ProjectionExpression** specify the properties you want in the scan results.

**FilterExpression** specifies a condition that returns only items that satisfy the condition. All other items are removed.

3. Run the program using the authenticated and configured **Window Command Prompt** in [step 3.1 Configure AWS CLI](../../3.1-configureawscli/). Type command:

```
python MoviesScan.py
```
Another case: use **`python "MoviesScan.py file path"`**

4. After running the program, get the result

```

1958 : Cat on a Hot Tin Roof
{'rating': Decimal('8')}

1958 : Monster on the Campus
{'rating': Decimal('5.7')}

1958 : No Time for Sergeants
{'rating': Decimal('7.5')}

1958 : Teacher's Pet
{'rating': Decimal('7')}

1958 : Touch of Evil
{'rating': Decimal('8.2')}

1958 : Vertigo
{'rating': Decimal('8.5')}

1951 : A Streetcar Named Desire
{'rating': Decimal('8')}

1951 : Alice in Wonderland
{'rating': Decimal('7.4')}

1951 : An American in Paris
{'rating': Decimal('7.2')}

1951 : Operation Pacific
{'rating': Decimal('6.5')}

1951 : Storm Warning
{'rating': Decimal('7')}

1951 : Strangers on a Train
{'rating': Decimal('8.2')}

1951 : The African Queen
{'rating': Decimal('8')}

```