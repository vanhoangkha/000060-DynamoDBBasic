---
title : "Load sample data"
date : "`r Sys.Date()`"
weight : 6
chapter : false
pre : " <b> 3.2.6 </b> "
---

1. Download sample data.


{{%notice tip%}}
[Download](https://github.com/HungNG-AWS/fcjsample/blob/aa1f636f4ccd8302f01ff0bbb18ecd14f429bb21/moviedata.zip)
{{%/notice%}}

2. Extract the data file (**moviedata.json**) from the archive.

3. Copy the file **moviedata.json** to your current directory.

4. Create a file named **`MoviesLoadData.py`**

5. Copy the following code and paste it into the file **`MoviesLoadData.py`**

```
from decimal import Decimal
import json
import boto3


def load_movies(movies, dynamodb=None):
    dynamodb = boto3.resource('dynamodb')
    table = dynamodb.Table('Movies')
    for movie in movies:
        year = int(movie['year'])
        title = movie['title']
        print("Adding movie:", year, title)
        table.put_item(Item=movie)


if __name__ == '__main__':
    with open("moviedata.json") as json_file:
        movie_list = json.load(json_file, parse_float=Decimal)
    load_movies(movie_list)

```
6. Run the program using the authenticated and configured **Window Command Prompt** in [step 3.1 Configure AWS CLI](../../3.1-configureawscli/). Type command:

```
python MoviesLoadData.py
```
Another case: use **`python "MoviesLoadData.py file path"`**

7. After running the program, get the following results:
```
Adding movie: 2013 Insidious: Chapter 2
Adding movie: 2013 World War Z
Adding movie: 2014 X-Men: Days of Future Past
Adding movie: 2014 Transformers: Age of Extinction
Adding movie: 2013 Now You See Me
Adding movie: 2013 Gravity
Adding movie: 2013 We're the Millers
Adding movie: 2013 Riddick
Adding movie: 2013 The Family
Adding movie: 2013 Star Trek Into Darkness
Adding movie: 2013 After Earth
Adding movie: 2013 The Great Gatsby
Adding movie: 2014 Divergent
Adding movie: 2013 We Are What We Are
Adding movie: 2013 Iron Man 3
Adding movie: 2014 The Amazing Spider-Man 2
Adding movie: 2013 Curse of Chucky
Adding movie: 2013 The Conjuring
Adding movie: 2013 Oldboy
Adding movie: 2013 Escape Plan
Adding movie: 2013 Elysium
Adding movie: 2013 Cloudy with a
```
Note: Correct file path **`moviedata.json`**