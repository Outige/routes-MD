# User routes

## `get_all_users`

```
Brief: This function will return all the user data in the `users` table
```

```
Route: /api/users/get/all
```

```
Method: GET
```

```
Input: null
```

```
Output:
[
    {
        "user_id": 38,
        "username": "Shaunty",
        "email": "shaun.oen.wp@gmail.com",
        "password": "$2a$10$3VQu3dZsmeuUM2rFD8XgzOxHYyyrWsRoVbusG6Mcvhf1KIf2ThHv6"
    },...
]
```

### Status codes

```
200: Status OK
* The request was successful. The whole of the `users` table should be returned as specified
```

```
500: Internal error
* Something went wrong server side
```
---

## `get_users_by_username`

```
Brief: This function will return all the user data in the `users` table - that partially match the username in the URL
```

```
Route: /api/users/get/all/username/{username}
```

```
Method: GET
```

```
Input: /api/users/get/all/username/user42
```

```
Output:
[
    {
        "user_id": 39,
        "username": "user420",
        "email": "eee@gmail.com",
        "password": "$2a$10$bPGwQeLZnEa9QKL477TsPe2cgnUaPy.e7UZH4KylY4QOifW9x1bN2"
    },...
]
```

### Status codes

```
200: Status OK
* The request was successful. The user data will be returned
```

```
400: Bad request
* The username entered resulted in no db hits. Nothing to return
```

```
500: Internal error
* Something went wrong server side
```
---

## `get_users_by_id`

```
Brief: This function will return all the user data in the `users` table - that exactly match the ID in the URL
```

```
Route: /api/users/get/single/id/{id}
```

```
Method: GET
```

```
Input: /api/users/get/single/id/39
```

```
Output:
[
    {
        "user_id": 39,
        "username": "user420",
        "email": "eee@gmail.com",
        "password": "$2a$10$bPGwQeLZnEa9QKL477TsPe2cgnUaPy.e7UZH4KylY4QOifW9x1bN2"
    }
]
```

### Status codes

```
200: Status OK
* The request was successful. The user data will be returned
```

```
400: Bad request
* The ID entered resulted in no db hits. Nothing to return
```

```
500: Internal error
* Something went wrong server side
```
---

## `delete_user`

```
Brief: This function will delete the user specified by the ID in the URL
```

```
Route: /api/users/delete/single/id/{user_id}
```

```
Method: DELETE
```

```
Input: null
```

```
Output: null
```

### Status codes

```
200: Status OK
* The request was successful. The user was deleted
```

```
400: Bad request
* The ID entered resulted in no db hits
```

```
500: Internal error
* Something went wrong server side
```


# Friend routes

## `add a friend`

```
Brief: Create a new friend relationship
```

```
Route: /api/friends/create
```

```
Method: POST
```

```
Input:
{
	"user_id":40,
	"friend_id":43
}
```

```
Output: null
```

### Status codes

```
200: Status OK
* The request was successful
```

```
400: Bad request
* users don't exist
* users are already friends
```

```
500: Internal error
* Something went wrong server side
```
---

## `get all friends`

```
Brief: Return all the friends relationships
```

```
Route: /api/friends/get/all
```

```
Method: GET
```

```
Input: null
```

```
Output:
[
    {
        "user_id": 40,
        "friend_id": 41
    },...
]
```

### Status codes

```
200: Status OK
* The request was successful
```

```
500: Internal error
* Something went wrong server side
```
---

## `get all friends of a user by id`

```
Brief: Return all the friends relationships of a specific user
```

```
Route: /api/friends/get/all/id/{user_id}
```

```
Method: GET
```

```
Input: /api/friends/get/all/id/40
```

```
Output:
[
    {
        "user_id": 40,
        "friend_id": 41
    },...
]
```

### Status codes

```
200: Status OK
* The request was successful
```

```
400: Bad request
* No hits with supplied user_id
```

```
500: Internal error
* Something went wrong server side
```
---
## `delete friendship`

```
Brief: delete a friend of a user
```

```
Route: /api/friends/delete
```

```
Method: DELETE
```

```
Input:
{
	"user_id":40,
	"friend_id":43
}
```

```
Output: null
```

### Status codes

```
200: Status OK
* The request was successful
```

```
400: Bad request
* No hits with supplied user_id
```

```
500: Internal error
* Something went wrong server side
```

# Group routes

## `create a group`

```
Brief: creates a group
```

```
Route: /api/groups/create
```

```
Method: POST
```

```
Input:
{
	"name":"Group new",
	"description":"Group new is special",
	"user_id":40
}
```

```
Output: null
```

### Status codes

```
200: Status OK
* The request was successful
```

```
400: Bad request
* Not sure when this happens
```

```
500: Internal error
* Something went wrong server side
```
---
## `get all groups`

```
Brief: get all groups
```

```
Route: /api/groups/get/all
```

```
Method: GET
```

```
Input: null
```

```
Output:
[
    {
        "group_id": 5,
        "name": "UPD name",
        "description": "Updated description"
    },...
]
```

### Status codes

```
200: Status OK
* The request was successful
```

```
500: Internal error
* Something went wrong server side
```
---

## `get groups by name`
```
Brief: get all groups that partiall match the name entered in the url
```

```
Route: /api/groups/get/all/name/{name}
```

```
Method: GET
```

```
Input: /api/groups/get/all/name/up
```

```
Output:
[
    {
        "group_id": 5,
        "name": "UPD name",
        "description": "Updated description"
    },...
]
```

### Status codes

```
200: Status OK
* The request was successful
```

```
400: Bad request
* no hits on the name entered
```

```
500: Internal error
* Something went wrong server side
```
---

## `get group by id`
```
Brief: get all groups that partiall match the id entered in the url
```

```
Route: /api/groups/get/single/id/{id}
```

```
Method: GET
```

```
Input: /api/groups/get/single/id/5
```

```
Output:
[
    {
        "group_id": 5,
        "name": "UPD name",
        "description": "Updated description"
    }
]
```

### Status codes

```
200: Status OK
* The request was successful
```

```
400: Bad request
* no hits on the id entered
```

```
500: Internal error
* Something went wrong server side
```
---

## `update a group`
```
Brief: update a group
```

```
Route: /api/groups/update
```

```
Method: PUT
```

```
Input:
{
    "group_id":5,
    "name": "UPD name",
    "description": "Updated description",
    "user_id":40
}
```

```
Output:
[
    {
        "group_id": 5,
        "name": "UPD name",
        "description": "Updated description"
    }
]
```

### Status codes

```
200: Status OK
* The request was successful
```

```
400: Bad request
* user not admin
* no hits on the group
* description empty
```

```
500: Internal error
* Something went wrong server side
```
---

## `delete group`
```
Brief: delete a group
```

```
Route: /api/groups/delete
```

```
Method: DELETE
```

```
Input:
{
    "group_id":31,
    "user_id":40
}
```

```
Output: null
```

### Status codes

```
200: Status OK
* The request was successful
```

```
400: Bad request
* user not admin
* no hits on the group
```

```
500: Internal error
* Something went wrong server side
```
---

# Member routes
## `join a group`
```
Brief: add member
```

```
Route: /api/members/create
```

```
Method: POST
```

```
Input:
{
	"group_id":5,
	"user_id":3
}
```

```
Output: null
```

### Status codes

```
200: Status OK
* The request was successful
```

```
400: Bad request
* already a member
```

```
500: Internal error
* Something went wrong server side
```
---

## `admin/dis-admin a member`
## `join a group`
```
Brief: update the admin status of a member
```

```
Route: /api/members/update
```

```
Method: PUT
```

```
Input:
{
	"group_id":5,
	"user_id":0, // user doing the updating
	"admin":true,
	"effect_user":3 // user getting updated
}
```

```
Output: null
```

### Status codes

```
200: Status OK
* The request was successful
```

```
400: Bad request
* user doing the updating isn't an admin
* can't dis-admin yourslef
```

```
500: Internal error
* Something went wrong server side
```
---

## remove a user from a group
```
Brief: delete a member
```

```
Route: /api/members/delete
```

```
Method: DELETE
```

```
Input:
{
	"group_id":5,
	"user_id":0, // user doing the deleting
	"effect_user":3 // user getting deleted
}
```

```
Output: null
```

### Status codes

```
200: Status OK
* The request was successful
```

```
400: Bad request
* user doing the deleting isn't an admin and isn't the same user
```

```
500: Internal error
* Something went wrong server side
```
---

# Post routes
## `create a post`
```
Brief: creates a post
```

```
Route: /api/posts/create
```

```
Method: POST
```

```
Input:
{
	"body":"Posty",
	"location":"x=20 y=20",
	"time":"1999-01-08 04:05:06",
	"group_id":5,
	"user_id":1,
    "tags": [
    "Tag 0",
    "tag me",
    "Tag 1"
	]
}
```

```
Output: null
```

### Status codes

```
200: Status OK
* The request was successful
```

```
400: Bad request
* not in group
* too few tags
* empty tags
```

```
500: Internal error
* Something went wrong server side
```
---

## `get all posts`
```
Brief: get all posts
```

```
Route: /api/posts/get/all
```

```
Method: GET
```

```
Input: null
```

```
Output:
[
    {
        "id": 10,
        "body": "new bodyy",
        "location": "x=20 y=20",
        "time": "2000-01-08T04:05:06Z",
        "group_id": 5,
        "user_id": 0,
        "tags": [
            "Tag a",
            "tag p",
            "Tag papi"
        ],
        "comments": [
            {
                "id": 2,
                "body": "comment 0",
                "time": "0999-01-08T04:05:06Z",
                "post_id": 10,
                "user_id": 1
            },...
        ]
    },...
]
```

### Status codes

```
200: Status OK
* The request was successful
```

```
500: Internal error
* Something went wrong server side
```
---

## `update a post`
```
Brief: update a post
```

```
Route: /api/posts/update
```

```
Method: PUT
```

```
Input:
{
	"id":10,
	"body":"new bodyy",
	"time":"2000-01-08 04:05:06",
	"user_id":0,
	 "tags": [
	    "Tag a",
	    "tag p",
	    "Tag papi"
	]
}
```

```
Output: null
```

### Status codes

```
200: Status OK
* The request was successful
```

```
500: Internal error
* Something went wrong server side
```
---

## `delete a post`
```
Brief: delete a post
```

```
Route: /api/posts/delete
```

```
Method: DELETE
```

```
Input:
{
	"id":14,
	"group_id":5,
	"user_id":40
}
```

```
Output: null
```

### Status codes

```
200: Status OK
* The request was successful
```

```
400: Bad request
```

```
500: Internal error
* Something went wrong server side
```

# Comment routes

## `create a comment`

```
Route: /api/comments/create
```

```
Method: POST
```

```
Input:
{
	"body":"comment body",
	"time":"999-01-08T04:05:06Z",
	"post_id":10,
	"user_id":40
}
```

```
Output: null
```

### Status codes

```
200: Status OK
* The request was successful
```

```
400: Bad request
```

```
500: Internal error
* Something went wrong server side
```

## `update a comment`

```
Route: /api/comments/update
```

```
Method: PUT
```

```
Input:
{
	"id":3,
	"user_id":1,
	"body":".",
	"time":"0999-01-08T04:05:06Z"
}
```

```
Output: null
```

### Status codes

```
200: Status OK
* The request was successful
```

```
400: Bad request
```

```
500: Internal error
* Something went wrong server side
```

## `delete a comment`
```
Route: /api/comments/delete
```

```
Method: DELETE
```

```
Input:
{
	"id":3,
	"user_id":1
}
```

```
Output: null
```

### Status codes

```
200: Status OK
* The request was successful
```

```
400: Bad request
```

```
500: Internal error
* Something went wrong server side
```
---


# More post routes
## `get a post by group`

```
Route: /api/posts/get/all/group/{group_id}
```

```
Method: GET
```

```
Input: http://localhost:8000/api/posts/get/all/group/5
```

```
Output:
[
    {
        "id": 16,
        "body": "Post0",
        "location": "x=20 y=20",
        "time": "1999-01-08 04:05:06",
        "group_id": 5,
        "user_id": 1,
        "username": "u1",
        "tags": null,
        "comments": null
    },...
]
```

### Status codes

```
200: Status OK
* The request was successful
```

```
400: Bad request
* no db hits
```

```
500: Internal error
* Something went wrong server side
```
---

## `get a post by user_id`

```
Route: http://localhost:8000/api/posts/get/all/user/{user_id}
```

```
Method: GET
```

```
Input: http://localhost:8000/api/posts/get/all/user/1
```

```
Output:
[
    {
        "id": 16,
        "body": "Post0",
        "location": "x=20 y=20",
        "time": "1999-01-08 04:05:06",
        "group_id": 5,
        "user_id": 1,
        "username": "u1",
        "tags": null,
        "comments": null
    },...
]
```

### Status codes

```
200: Status OK
* The request was successful
```

```
400: Bad request
* no db hits
```

```
500: Internal error
* Something went wrong server side
```
---

## `get a post by tags`
```
Route: /api/posts/get/all/tag
```

```
Method: GET
```

```
Input:
{
	"hashtag":"Tag m"
}
```

```
Output:
[
    {
        "id": 29,
        "body": "Posty",
        "location": "x=20 y=20",
        "time": "1999-01-08 04:05:06",
        "group_id": 5,
        "user_id": 1,
        "username": "u1",
        "tags": [
            "Tag 0",
            "tag me",
            "Tag 1"
        ],
        "comments": null
    },...
]
```

### Status codes

```
200: Status OK
* The request was successful
```

```
400: Bad request
* no db hits
```

```
500: Internal error
* Something went wrong server side
```
---

## `get a post by friendship`
```
Route: /api/posts/get/all/friend
```

```
Method: GET
```

```
Input:
{
	"user_id":40
}
```

```
Output:
[
    {
        "id": 29,
        "body": "Posty",
        "location": "x=20 y=20",
        "time": "1999-01-08 04:05:06",
        "group_id": 5,
        "user_id": 1,
        "username": "u1",
        "tags": [
            "Tag 0",
            "tag me",
            "Tag 1"
        ],
        "comments": null
    },...
]
```

### Status codes

```
200: Status OK
* The request was successful
```

```
400: Bad request
* no db hits
```

```
500: Internal error
* Something went wrong server side
```
---

## `get all posts by time`
```
Route: /api/posts/get/all/time
```

```
Method: GET
```

```
Input:
```

```
Output:
[
    {
        "id": 29,
        "body": "Posty",
        "location": "x=20 y=20",
        "time": "1999-01-08 04:05:06",
        "group_id": 5,
        "user_id": 1,
        "username": "u1",
        "tags": [
            "Tag 0",
            "tag me",
            "Tag 1"
        ],
        "comments": null
    },...
]
```

### Status codes

```
200: Status OK
* The request was successful
```

```
400: Bad request
* no db hits
```

```
500: Internal error
* Something went wrong server side
```
---

## `get post by distance - radius for map`
```
Route: /api/posts/get/all/distance/radius
```

```
Method: GET
```

```
Input: /api/posts/get/all/distance/radius?ty
{
	"location":"50 03 59N, 005 42 53W",
	"radius":900
}
```

```
Output:
[
    {
        "id": 29,
        "body": "Posty",
        "location": "x=20 y=20",
        "time": "1999-01-08 04:05:06",
        "group_id": 5,
        "user_id": 1,
        "username": "u1",
        "tags": [
            "Tag 0",
            "tag me",
            "Tag 1"
        ],
        "comments": null
    },...
]
```

### Status codes

```
200: Status OK
* The request was successful
```

```
400: Bad request
* no db hits
```

```
500: Internal error
* Something went wrong server side
```
---

## `get post by distance - neasrist list`
```
Route: /api/posts/get/all/distance
```

```
Method: GET
```

```
Input:
{
	"location":"50 03 59N, 005 42 53W"
}
```

```
Output:
[
    {
        "id": 31,
        "body": "The lab is a lie",
        "location": "50 03 59N, 005 42 53W",
        "time": "2016-06-22 19:10:25",
        "group_id": 5,
        "user_id": 0,
        "username": "u0",
        "Distance": 0,
        "tags": [
            "Tag 0",
            "tag me",
            "Tag 1"
        ],
        "comments": null
    },...
]
```

### Status codes

```
200: Status OK
* The request was successful
```

```
400: Bad request
* no db hits
```

```
500: Internal error
* Something went wrong server side
```
---