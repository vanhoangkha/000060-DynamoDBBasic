---
title : "Delete the table"
date : "`r Sys.Date()`"
weight : 9
chapter : false
pre : " <b> 3.2.9 </b> "
---

1. Create a file named **`MoviesDeleteTable.py`**

2. Copy the following code and paste it into **`MoviesDeleteTable.py`**
```
import boto3


def delete_movie_table(dynamodb=None):
     dynamodb = boto3.resource('dynamodb')
     table = dynamodb.Table('Movies')
     table.delete()


if __name__ == '__main__':
     delete_movie_table()
     print("Movies table deleted.")
```
3. Run the program using the authenticated and configured **Window Command Prompt** in [step 3.1 Configure AWS CLI](../../3.1-configureawscli/). Type command:

```
python MoviesDeleteTable.py
```
Another case: use **`python "MoviesDeleteTable.py file path"`**

4. After running the program, get the result

```
Movies table deleted.

```
