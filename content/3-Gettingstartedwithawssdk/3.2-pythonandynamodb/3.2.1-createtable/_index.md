---
title : "Create table"
date : "`r Sys.Date()`"
weight : 1
chapter : false
pre : " <b> 3.2.1 </b> "
---

In this step, we create a table named **Movies**. The primary key for the table includes the following attributes:

**year** – The partition key. AttributeType is N(number).

**title** – The sort key. AttributeType is S(string).

1. Create a file named **`MoviesCreateTable.py`**

2. Copy the following code and paste it into the file **`MoviesCreateTable.py`**

```
import boto3


def create_movie_table(dynamodb=None):
    dynamodb = boto3.resource('dynamodb')
    table = dynamodb.create_table(
        TableName='Movies',
        KeySchema=[
            {
                'AttributeName': 'year',
                'KeyType': 'HASH' # Partition key
            },
            {
                'AttributeName': 'title',
                'KeyType': 'RANGE' # Sort key
            }
        ],
        AttributeDefinitions=[
            {
                'AttributeName': 'year',
                'AttributeType': 'N'
            },
            {
                'AttributeName': 'title',
                'AttributeType': 'S'
            },

        ],
        ProvisionedThroughput={
            'ReadCapacityUnits': 10,
            'WriteCapacityUnits': 10
        }
    )
    return table


if __name__ == '__main__':
    movie_table = create_movie_table()
    print("Table status:", movie_table.table_status)

```

3. Run the program using the authenticated and configured **Window Command Prompt** in [step 3.1 Configure AWS CLI](../../3.1-configureawscli/). Type command:
  
```
python MoviesCreateTable.py
```
Another case: use **`python "MoviesCreateTable.py file path"`**

4. After running the program, **`Table status: CREATING`** is returned to the successful creation of the table.