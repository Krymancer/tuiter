# Database

This section is about the database design for the application.

## Tools

SQlite is a library that implements a fast, self-contained and full-featured SQL database engine. As is simple was the perfect choise for the proof of concept that will be developed.

## Schema

As a twitter clone we will need some features, we have two major entities: Users and Tweets.

A user has be able to:

- Login
- Create a new tweet 
- Reply a tweet
- Like a tweet
- Unlike a tweet
- Follow another Users
- Search other Users
- See another user profile
- See their profile
- Edit their profile


We imagine a user been stored in the database as:

| Column     | Type                         | Description                              | 
|:-----------|:-----------------------------|:-----------------------------------------|
| id         | text(100) PK Not Null        | Uuid stored as string                    |
| username   | text(100) Not Null Unique    | username, no special characters          |
| hash       | text(500) Not Null           | hashed password                          |
| icon       | text(500)                    | image url to be displayed as profile pic |
| bio        | text(256)                    | small about user, displayed in profile   |
| created_at | datetime  Not Null           | datetime that user was created           |

And a tweet:

| Column     | Type                  | Description                    |
|:-----------|:----------------------|:-------------------------------|
| id         | text(100) PK Not Null | Uuid stored as string          | 
| content    | text(256) Not Null    | content stored as string       |
| author     | text(100) FK Not Null | foreing key, refereces a user  |
| created_at | datetime Not Null     | datetime that tweet as created | 

We derive other tables relation these two main entities:

Followers

| Column     | Type                  | Description                                                  |
|:-----------|:----------------------|:-------------------------------------------------------------|
| id         | text(100) PK Not Null | Uuid stored as string                                        | 
| follower  | text(100) FK Not Null | foreing key, reference a user that follow target user        |
| target     | text(100) FK Not Null | foreing key, references a user that is followed by following |


Likes

| Column     | Type                  | Description                                                  |
|:-----------|:----------------------|:-------------------------------------------------------------|
| id         | text(100) PK Not Null | Uuid stored as string                                        | 
| tweet      | text(100) FK Not Null | foreing key, reference a tweet                               |
| user       | text(100) FK Not Null | foreing key, references a user that liked the tweet          |

Replies

| Column       | Type                  | Description                                                  |
|:-------------|:----------------------|:-------------------------------------------------------------|
| id           | text(100) PK Not Null | Uuid stored as string                                        | 
| tweet        | text(100) FK Not Null | foreing key, reference a tweet                               |
| author       | text(100) FK Not Null | foreing key, references a user that liked the tweet          |
| content      | text(256) Not Null    | content stored as string                                     |


