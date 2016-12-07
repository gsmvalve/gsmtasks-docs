# Clients

## List Clients

Returns a array of clients that the user has access to.

> The request returns JSON structured like this:

```json
[
    {
        "id": "74c08598-08b8-46bc-9da7-8b85f7168f20",
        "url": "https://gsmtasks.com/api/tasks/clients/74c08598-08b8-46bc-9da7-8b85f7168f20/",
        "account": "https://gsmtasks.com/api/tasks/accounts/798d8fda-43d1-497a-b63b-1ad784afc117/",
        "name": "Client",
        "slug": "client",
        "archived": false,
        "created_at": "2016-10-05T13:31:10.305811Z",
        "updated_at": "2016-10-06T08:50:21.366881Z"
    }
]
```

`GET https://gsmtasks.com/api/tasks/clients/`

### Attributes

Attribute     | Type   | Description
------------  | ------ | -----------
id            | String | Client unique identifier
url           | String | Unique URL for the resource
account       | String | URL of the account resource
name          | String | Name of the client
slug          | String | Machine readable account identifier
archived      | Boolean| Shows whether the client is archived or not
created_at    | String | The time when the order was created
updated_at    | String | The time when the order was updated

## Retrieve a specific Client

`GET https://gsmtasks.com/api/tasks/clients/74c08598-08b8-46bc-9da7-8b85f7168f20/`

## Create Client

Request to create a new Client with the parameters provided.

> Example POST request JSON data:

```json
{
    "account": "https://gsmtasks.com/api/tasks/accounts/798d8fda-43d1-497a-b63b-1ad784afc117/",
    "name": "Client",
    "archived": false
}
```

> The request returns JSON of the created Order structured like this:

```json
{
    "id": "74c08598-08b8-46bc-9da7-8b85f7168f20",
    "url": "https://gsmtasks.com/api/tasks/clients/74c08598-08b8-46bc-9da7-8b85f7168f20/",
    "account": "https://gsmtasks.com/api/tasks/accounts/798d8fda-43d1-497a-b63b-1ad784afc117/",
    "name": "Client",
    "slug": "client",
    "archived": false,
    "created_at": "2016-10-05T13:31:10.305811Z",
    "updated_at": "2016-10-06T08:50:21.366881Z"
}
```

`POST https://gsmtasks.com/api/tasks/clients/`

### Request parameters

Parameter     | Type   | Required | Description
------------  | ------ | -------  | -----------
account       | String | Yes      | URL of the account resource
name          | String | Yes      | Name of the client
archived      | String | Yes      | Shows whether the client is archived or not


## Update Client

Request to update a Client. We will change the name and the archived status as an example.

> Example PUT request JSON data:

```json
{
    "account": "https://gsmtasks.com/api/tasks/accounts/798d8fda-43d1-497a-b63b-1ad784afc117/",
    "name": "Another client",
    "archived": true
}
```

> The request returns JSON of the updated Order structured like this:

```json
{
    "id": "74c08598-08b8-46bc-9da7-8b85f7168f20",
    "url": "https://gsmtasks.com/api/tasks/clients/74c08598-08b8-46bc-9da7-8b85f7168f20/",
    "account": "https://gsmtasks.com/api/tasks/accounts/798d8fda-43d1-497a-b63b-1ad784afc117/",
    "name": "Another client",
    "slug": "client",
    "archived": true,
    "created_at": "2016-10-05T13:31:10.305811Z",
    "updated_at": "2016-10-06T08:50:21.366881Z"
}
```

`PUT https://gsmtasks.com/api/tasks/clients/74c08598-08b8-46bc-9da7-8b85f7168f20/`

### Request parameters

Parameter     | Type   | Required | Description
------------  | ------ | -------  | -----------
account       | String | Yes      | URL of the account resource
name          | String | Yes      | Name of the client
archived      | String | No       | Shows whether the client is archived or not

