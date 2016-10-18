# Users

## List Users

Returns a array of users. The users returned are the users to whom you have access through different accounts.

> The request returns JSON structured like this:

```json
[
    {
        "id": "835cdcf8-9d1e-4718-ad47-4cf0a63626b4",
        "url": "http://127.0.0.1:8000/api/tasks/users/835cdcf8-9d1e-4718-ad47-4cf0a63626b4/",
        "first_name": "Tom",
        "last_name": "Smith",
        "display_name": "Tom Smith",
        "email": "tom.smith@fast.uk",
        "phone": "+447700900132"
    }
]
```

`GET https://gsmtasks.com/api/tasks/users/`

### Attributes

Attribute     | Type    | Required | Description
------------  | ------- | -------  | -----------
id            | String  | -        | Account Role unique identifier
url           | String  | -        | Unique URL for the resource
first_name    | String  | -        | First name of the user
last_name     | String  | -        | Last name of the user
display_name  | String  | -        | Display name of the user
email         | String  | -        | Email of the user
phone         | String  | -        | International phone number of the user

## Retrieve a specific User

`GET https://gsmtasks.com/api/tasks/users/12d2821e-01e2-48fb-97bc-eaebca93cbdc/`


## Create User

Request to create a new user with the parameters provided

> Example POST request JSON data:

```json
{
  "first_name": "Tom",
  "last_name": "Smith",
  "email": "tom.smith@fast.uk",
  "phone": "+447700900132"
}
```

> The request returns JSON of the created User structured like this:

```json
{
    "id": "835cdcf8-9d1e-4718-ad47-4cf0a63626b4",
    "url": "http://127.0.0.1:8000/api/tasks/users/835cdcf8-9d1e-4718-ad47-4cf0a63626b4/",
    "first_name": "Tom",
    "last_name": "Smith",
    "display_name": "Tom Smith",
    "email": "tom.smith@fast.uk",
    "phone": "+447700900132"
}
```

`POST https://gsmtasks.com/api/tasks/users/`

### Request parameters

Parameter        | Type    | Required | Description
---------------- | ------- | -------  | -----------
first_name       | String  | -        | First name of the user
last_name        | String  | -        | Last name of the user
email            | String  | -        | Email of the user
phone            | String  | -        | International phone number of the user
