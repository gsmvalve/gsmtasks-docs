# Orders

Orders are to group together some tasks (waypoints) that need to be completed to full fill the order.

## List Orders

Returns a array of orders that the user has access to.

> The request returns JSON structured like this:

```json
[
  {
    "id": "4336f911-32ec-4fb4-b17a-e58aef3943e6",
    "url": "https://gsmtasks.com/api/tasks/orders/4336f911-32ec-4fb4-b17a-e58aef3943e6/",
    "account": "https://gsmtasks.com/api/tasks/accounts/4368ec5d-9942-4c74-90f7-eea752a6e489/",
    "external_id": "123ABC",
    "reference": "ABCD",
    "client": "https://gsmtasks.com/api/tasks/clients/74c08598-08b8-46bc-9da7-8b85f7168f20/",
    "tasks": [
      "https://gsmtasks.com/api/tasks/tasks/353ce213-c649-4e4b-bbcf-a493433cee9c/"
      "https://gsmtasks.com/api/tasks/tasks/d0de6a56-e8ae-4ac9-983e-ef1486909ce7/"
    ],
    "auto_assign": true,
    "created_at": "2016-10-10T09:36:22.190884Z",
    "updated_at": "2016-10-10T09:48:19.376249Z"
  }
]
```

`GET https://gsmtasks.com/api/tasks/orders/`

### Attributes

Attribute     | Type   | Description
------------  | ------ | -----------
id            | String | Order unique identifier
url           | String | Unique URL for the resource
account       | String | URL of the account resource
external_id   | String | External id of the order
reference     | String | Reference of the order
client        | String | URL of the client
tasks         | Array  | Tasks that need to be completed
auto_assign   | Boolean| Should the tasks be auto assigned to a driver
created_at    | String | The time when the order was created
updated_at    | String | The time when the order was updated

## Retrieve a specific Order

`GET https://gsmtasks.com/api/tasks/orders/4336f911-32ec-4fb4-b17a-e58aef3943e6/`

## Create Order

Request to create a new order with the parameters provided. The tasks that are going to be attached to the order need to be created beforehand or add the tasks later by updating the order.

You can read more about creating tasks [here](#tasks).

> Example POST request JSON data:

```json
{
  "account": "https://gsmtasks.com/api/tasks/accounts/4368ec5d-9942-4c74-90f7-eea752a6e489/",
  "external_id": "123456",
  "reference": "reference",
  "client": "https://gsmtasks.com/api/tasks/clients/74c08598-08b8-46bc-9da7-8b85f7168f20/", 
  "tasks": [
    "https://gsmtasks.com/api/tasks/tasks/353ce213-c649-4e4b-bbcf-a493433cee9c/"
    "https://gsmtasks.com/api/tasks/tasks/d0de6a56-e8ae-4ac9-983e-ef1486909ce7/"
  ],
  "auto_assign": true
}
```

> The request returns JSON of the created Order structured like this:

```json
{
  "id": "4336f911-32ec-4fb4-b17a-e58aef3943e6",
  "url": "https://gsmtasks.com/api/tasks/orders/4336f911-32ec-4fb4-b17a-e58aef3943e6/",
  "account": "https://gsmtasks.com/api/tasks/accounts/4368ec5d-9942-4c74-90f7-eea752a6e489/",
  "external_id": "123456",
  "reference": "reference",
  "client": "https://gsmtasks.com/api/tasks/clients/74c08598-08b8-46bc-9da7-8b85f7168f20/", 
  "tasks": [
    "https://gsmtasks.com/api/tasks/tasks/353ce213-c649-4e4b-bbcf-a493433cee9c/"
    "https://gsmtasks.com/api/tasks/tasks/d0de6a56-e8ae-4ac9-983e-ef1486909ce7/"
  ],
  "auto_assign": true,
  "created_at": "2016-10-18T11:27:23.043743Z",
  "updated_at": "2016-10-18T11:27:23.043774Z"
}
```

`POST https://gsmtasks.com/api/tasks/orders/`

### Request parameters

Parameter     | Type   | Required | Description
------------  | ------ | -------  | -----------
account       | String | Yes      | URL of the account resource
external_id   | String | No       | External id of the order
reference     | String | No       | Reference of the order
client        | String | No       | URL of the client
tasks         | Array  | No       | Tasks that need to be completed referenced by the URLs
auto_assign   | Boolean| No       | Should the tasks be auto assigned to a driver

## Update Order

Request to update a order. We will add a task to the tasks array as an example.

<aside class="warning">
You can not remove the tasks from the order that have already been completed or cancelled.
</aside>

> Example PUT request JSON data:

```json
{
  "account": "https://gsmtasks.com/api/tasks/accounts/4368ec5d-9942-4c74-90f7-eea752a6e489/",
  "tasks": [
    "https://gsmtasks.com/api/tasks/tasks/353ce213-c649-4e4b-bbcf-a493433cee9c/"
    "https://gsmtasks.com/api/tasks/tasks/d0de6a56-e8ae-4ac9-983e-ef1486909ce7/"
    "https://gsmtasks.com/api/tasks/tasks/850b2503-6466-41ae-9073-5e994688b812/"
  ]
}
```

> The request returns JSON of the updated Order structured like this:

```json
{
  "id": "4336f911-32ec-4fb4-b17a-e58aef3943e6",
  "url": "https://gsmtasks.com/api/tasks/orders/4336f911-32ec-4fb4-b17a-e58aef3943e6/",
  "account": "https://gsmtasks.com/api/tasks/accounts/4368ec5d-9942-4c74-90f7-eea752a6e489/",
  "external_id": "123456",
  "reference": "reference",
  "client": "https://gsmtasks.com/api/tasks/clients/74c08598-08b8-46bc-9da7-8b85f7168f20/", 
  "tasks": [
    "https://gsmtasks.com/api/tasks/tasks/353ce213-c649-4e4b-bbcf-a493433cee9c/"
    "https://gsmtasks.com/api/tasks/tasks/d0de6a56-e8ae-4ac9-983e-ef1486909ce7/"
    "https://gsmtasks.com/api/tasks/tasks/850b2503-6466-41ae-9073-5e994688b812/"
  ],
  "auto_assign": true,
  "created_at": "2016-10-18T11:27:23.043743Z",
  "updated_at": "2016-10-18T11:27:23.043774Z"
}
```

`PUT https://gsmtasks.com/api/tasks/orders/4336f911-32ec-4fb4-b17a-e58aef3943e6/`

### Request parameters

Parameter     | Type   | Required | Description
------------  | ------ | -------  | -----------
account       | String | Yes      | URL of the account resource
tasks         | Array  | No       | Tasks that need to be completed
external_id   | String | No       | External id of the order
reference     | String | No       | Reference of the order
client        | String | No       | URL of the client resource
auto_assigne  | Boolena| No       | Should the tasks be auto assigned to a driver
