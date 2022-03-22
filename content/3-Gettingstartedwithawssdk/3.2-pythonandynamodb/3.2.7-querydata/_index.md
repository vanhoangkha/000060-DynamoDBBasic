---
title : "Query data"
date : "`r Sys.Date()`"
weight : 7
chapter : false
pre : " <b> 3.2.7 </b> "
---

Retrieve all movies released in 1985 from sample data uploaded at [3.2.6 Load sample data](../3.2.6-loadsampledata/)


1. Create a file named **`MoviesQuery01.py`**

2. Copy the following code and paste it into **`MoviesQuery01.py`**
  
```
import boto3
from boto3.dynamodb.conditions import Key


def query_movies(year, dynamodb=None):
    dynamodb = boto3.resource('dynamodb')
    table = dynamodb.Table('Movies')
    response = table.query(
        KeyConditionExpression=Key('year').eq(year)
    )
    return response['Items']


if __name__ == '__main__':
    query_year = 1985
    print(f"Movies from {query_year}")
    movies = query_movies(query_year)
    for movie in movies:
        print(movie['year'], ":", movie['title'])

```
3. Run the program using the authenticated and configured **Window Command Prompt** in [step 3.1 Configure AWS CLI](../../3.1-configureawscli/). Type command:

```
python MoviesQuery01.py
```
Another case: use **`python "MoviesQuery01.py file path"`**

4. After running the program, get the following results:

```
Movies from 1985
1985 : A Nightmare on Elm Street Part 2: Freddy's Revenge
1985 : A Room with a View
1985 : A View to a Kill
1985 : Back to the Future
1985 : Better Off Dead...
1985 : Brazil
1985 : Clue
1985 : Cocoon
1985 : Commando
1985 : Day of the Dead
1985 : Flesh+Blood
1985 : Friday the 13th: A New Beginning
1985 : Fright Night
1985 : Girls Just Want to Have Fun
1985 : Just One of the Guys
1985 : Legend
1985 : Mad Max Beyond Thunderdome
1985 : Mask
1985 : Pale Rider
1985 : Pee-wee's Big Adventure
1985 : Police Academy 2: Their First Assignment
1985 : Rambo: First Blood Part II
1985 : Real Genius
1985 : Return to Oz
1985 : Rocky IV
1985 : Silverado
1985 : St. Elmo's Fire
1985 : Teen Wolf
1985 : The Breakfast Club
1985 : The Color Purple
1985 : The Goonies
1985 : The Last Dragon
1985 : The Return of the Living Dead
1985 : Weird Science
1985 : Witness

```