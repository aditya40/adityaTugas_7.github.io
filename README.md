# adityaTugas_7.github.io

FORMAT: 1A
HOST: https://polls.apiblueprint.org/

# Blogging API

Simple API allowing consumers to view blogging authors, their posts and comments.

## Authors [/author]

### List All Authors [GET]

+ Response 200 (application/json)

        [
            {
                "id": "1",
                "username": "Mia Huljanah",
                "password": "Mia12345",
                "salt": "AkasnASNF121anSKNfaknfa",
                "email": "Mia@gmail.com",
                "profile": "Profile"
            },
            {
                "id": "2",
                "username": "Rashif Ilmi Nurzaman",
                "password": "Rashif12345",
                "salt": "AkasnASNF121anSKNfaknfa",
                "email": "Rashif@gmail.com",
                "profile": "Profile"
            },
            {
                "id": "3",
                "username": "Hardo Fernando Silalahi",
                "password": "Hardo12345",
                "salt": "AkasnASNF121anSKNfaknfa",
                "email": "Hardo@gmail.com",
                "profile": "Profile"
            }
        ]
        
### Create New Author [POST]

+ Request (application/json)

        {
            "username": "Fahmi Nur",
            "password": "fahmi12345",
            "email": "fahmi@gmail.com",
            "profile": "Profile"
        }

+ Response 201 (application/json)

    + Headers

            Location: /author/4

    + Body

            {
                "id": "4",
                "username": "Fahmi Nur",
                "password": "Fahmi12345",
                "salt": "AkasnASNF121anSKNfaknfa",
                "email": "fahmi@gmail.com",
                "profile": "Profile"
            }

## Authors Resource [/author/{id}]

+ Parameters
    + id : 1 (number, required) - An unique identifier of the message

### List Author with ID [GET]

+ Response 200 (application/json)

        [
            {
                "id": "1",
                "username": "Mia Huljanah",
                "password": "Mia12345",
                "salt": "AkasnASNF121anSKNfaknfa",
                "email": "Mia@gmail.com",
                "profile": "Profile"
            }
        ]

### Edit an Author [PATCH]

+ Request (application/json)

        {
            "email": "Mia@gmail.com"
        }

+ Response 201 (application/json)

        [
            {
                "id": "1",
                "username": "Mia Huljanah",
                "password": "Mia12345",
                "salt": "AkasnASNF121anSKNfaknfa",
                "email": "Mia@gmail.com",
                "profile": "Profile"
            }
        ]
        
### Delete an Author [DELETE]

+ Response 204


## Posts [/post]

### List All Posts [GET]


+ Response 200 (application/json)

        [
            {
                "id": "1",
                "title": "Title 1",
                "content": "content 1",
                "tags": "tags_1",
                "status": "Updated",
                "create_time": "2020-03-11T07:19:00.754Z",
                "update_time": "2020-03-11T07:20:00.754Z",
                "author_id": "1"
            },
            {
                "id": "2",
                "title": "Title 2",
                "content": "content 2",
                "tags": "tags2",
                "status": "Updated",
                "create_time": "2020-03-11T07:18:00.754Z",
                "update_time": "2020-03-11T07:20:00.754Z",
                "author_id": "2"
            },
            {
                "id": "3",
                "title": "Title 3",
                "content": "content 3",
                "tags": "tags3",
                "status": "Updated",
                "create_time": "2020-03-11T07:21:00.754Z",
                "update_time": "2020-03-11T07:23:00.754Z",
                "author_id": "3"
            }
        ]
        
### Create New Post [POST]

+ Request (application/json)

        {
            "title": "Title 4",
            "content": "content 4",
            "tags": "tags4",
            "author_id": "1"
        }

+ Response 201 (application/json)

    + Headers

            Location: /post/4

    + Body

            {
                "id": "4",
                "title": "Title 4",
                "content": "content 4",
                "tags": "tags4",
                "status": "Created",
                "create_time": "2020-03-11T07:23:00.754Z",
                "update_time": "",
                "author_id": "1"
            }
            
## Posts Resource [/post/{id}]

+ Parameters
    + id : 1 (number, required) - An unique identifier of the message

### List Post with ID [GET]

+ Response 200 (application/json)

        [
            {
                "id": "1",
                "title": "Title 1",
                "content": "content 1",
                "tags": "tags1",
                "status": "Updated",
                "create_time": "2020-03-11T07:19:00.754Z",
                "update_time": "2020-03-11T07:20:00.754Z",
                "author_id": "1"
            }
        ]

### Edit a Post [PATCH]

+ Request (application/json)

        {
            "content": "content 1a"
        }

+ Response 201 (application/json)

        [
            {
                "id": "1",
                "title": "Title 1",
                "content": "content 1a",
                "tags": "tags1",
                "status": "Updated",
                "create_time": "2020-03-11T07:19:00.754Z",
                "update_time": "2020-03-11T07:20:00.754Z",
                "author_id": "1"
            }
        ]
        
### Delete a Post [DELETE]

+ Response 204


## Comments [/comment]

### List All Comments [GET]


+ Response 200 (application/json)

        [
            {
                "id": "1",
                "content": "content 1",
                "status": "Updated",
                "create_time": "2020-03-11T07:21:52.754Z",
                "author_id": "1",
                "email": "Mia@gmail.com",
                "url": "Mia_huljah.com",
                "post_id": "2"
            },
            {
                "id": "2",
                "content": "content 2",
                "status": "Updated",
                "create_time": "2020-03-11T07:21:52.754Z",
                "author_id": "2",
                "email": "Rashif@gmail.com",
                "url": "rashif_ilmi.com",
                "post_id": "3"
            },
            {
                "id": "3",
                "content": "content 3",
                "status": "Updated",
                "create_time": "2020-03-11T07:21:52.754Z",
                "author_id": "3",
                "email": "Hardo@gmail.com",
                "url": "hardo_fernando.com",
                "post_id": "1"
            }
        ]

### Create New Comment [POST]

+ Request (application/json)

        {
            "content": "content 3",
            "author_id": "2",
            "email": "rashif_ilmi@email.com",
            "url": "rashif_ilmi.com",
            "post_id": "1"
        }

+ Response 201 (application/json)

    + Headers

            Location: /comment/4

    + Body

            {
                "id": "4",
                "content": "content 4",
                "status": "Created",
                "create_time": "2020-03-11T07:21:52.754Z",
                "author_id": "2",
                "email": "rashif_ilmi@email.com",
                "url": "rashif_ilmi.com",
                "post_id": "1"
            }
            
## Posts Resource [/comment/{id}]

+ Parameters
    + id : 1 (number, required) - An unique identifier of the message

### List Post with ID [GET]

+ Response 200 (application/json)

        [
            {
                "id": "1",
                "content": "content 1",
                "status": "Updated",
                "create_time": "2020-03-11T07:21:52.754Z",
                "author_id": "1",
                "email": "Mia@email.com",
                "url": "miahuljah.com",
                "post_id": "2"
            }
        ]

### Edit a Post [PATCH]

+ Request (application/json)

        {
            "content": "content 1a"
        }

+ Response 201 (application/json)

        [
            {
                "id": "1",
                "content": "content 1a",
                "status": "Updated",
                "create_time": "2020-03-11T07:21:52.754Z",
                "author_id": "1",
                "email": "Mia@gmail.com",
                "url": "miahuljah.com",
                "post_id": "2"
            }
        ]
        
### Delete a Post [DELETE]

+ Response 204
