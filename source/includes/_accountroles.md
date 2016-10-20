# Account Roles

## List Account Roles

Returns a array of account roles. Account Roles define the access to a specific account the user has been given.

Currently a very simple system is used and only two types of accesses can be given. Either *manager*, *worker* or both.

> The request returns JSON structured like this:

```json
[
  {
      "id": "dae7ab83-d6d9-4d83-acdf-e39890a8abe2",
      "url": "https://gsmtasks.com/api/tasks/roles/dae7ab83-d6d9-4d83-acdf-e39890a8abe2/",
      "account": "https://gsmtasks.com/api/tasks/accounts/4368ec5d-9942-4c74-90f7-eea752a6e489/",
      "user": "https://gsmtasks.com/api/tasks/users/18fb9d97-824b-4c2a-9b74-764a88a78c96/",
      "is_manager": false,
      "is_worker": true,
      "created_at": "2016-10-18T08:34:46.117131Z",
      "updated_at": "2016-10-18T08:34:46.117157Z"
  }
]
```

`GET https://gsmtasks.com/api/tasks/roles/`

### Attributes

Attribute     | Type    | Description
------------  | ------- | -----------
id            | String  | Account Role unique identifier
url           | String  | Unique URL for the resource
account       | String  | URL of the account resource
user          | String  | URL of the user resource
is_manager    | Boolean | Manager access boolean
is_worker     | Boolean | Worker access boolean
created_at   | String  | The time when the account role was created
updated_at    | String  | The time when the account role was updated


## Retrieve a specific Account Role

`GET https://gsmtasks.com/api/tasks/roles/dae7ab83-d6d9-4d83-acdf-e39890a8abe2/`

## Create Account Role

Request to create a new account role with the parameters provided

> Example POST request JSON data:

```json
{
    "account": "https://gsmtasks.com/api/tasks/accounts/4368ec5d-9942-4c74-90f7-eea752a6e489/",
    "user": "https://gsmtasks.com/api/tasks/users/18fb9d97-824b-4c2a-9b74-764a88a78c96/",
    "is_manager": false,
    "is_worker": true
}
```

> The request returns JSON of the created Account Role structured like this:

```json
{
    "id": "dae7ab83-d6d9-4d83-acdf-e39890a8abe2",
    "url": "https://gsmtasks.com/api/tasks/roles/dae7ab83-d6d9-4d83-acdf-e39890a8abe2/",
    "account": "https://gsmtasks.com/api/tasks/accounts/4368ec5d-9942-4c74-90f7-eea752a6e489/",
    "user": "https://gsmtasks.com/api/tasks/users/18fb9d97-824b-4c2a-9b74-764a88a78c96/",
    "is_manager": false,
    "is_worker": true,
    "created_at": "2016-10-20T12:55:33.977065Z",
    "updated_at": "2016-10-20T12:55:33.977092Z"
}
```

`POST https://gsmtasks.com/api/tasks/roles/`

### Request parameters

Parameter        | Type    | Required | Description
---------------- | ------- | -------  | -----------
account          | String  | Yes      | Name of the account for easy reference
user             | String  | Yes      | URL of the user resource
is_manager       | Boolean | -        | Manager access boolean
is_worker        | Boolean | -        | Worker access boolean
