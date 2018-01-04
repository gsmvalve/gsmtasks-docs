# Routes

Routes are to group together some tasks that need to be completed in the specified (optimized) sequence.

## List Routes

Returns a array of routes that the user has access to.

> The request returns JSON structured like this:

```json
[
  {
    "id": "31601953-2355-4192-8505-7c11ba65c53e",
    "url": "https://gsmtasks.com/api/tasks/routes/31601953-2355-4192-8505-7c11ba65c53e/",
    "account": "https://gsmtasks.com/api/tasks/accounts/4368ec5d-9942-4c74-90f7-eea752a6e489/",
    "code": "123ABC",
    "description": "The route I need to take",
    "assignee": "https://gsmtasks.com/api/tasks/users/cfdf3a8e-a9d7-4878-a922-344081a1ed75/",
    "start_time": "2018-01-04T16:39:48+02:00",
    "start_location": null,
    "end_time": null,
    "end_location": null,
    "created_at": "2018-01-04T16:39:57.006745+02:00",
    "updated_at": "2018-01-04T16:39:57.006767+02:00"
  }
]
```

`GET https://gsmtasks.com/api/tasks/routes/`

### Attributes

Attribute     | Type   | Description
------------  | ------ | -----------
id            | String | Route unique identifier
url           | String | Unique URL for the resource
external_id   | String | External id of the order
account       | String | URL of the account resource
code          | String | Reference of the route
description   | String | Description of the route details
assignee      | String | URL of the assignee resource
start_time    | String | Start time of the route
start_location| String | Start location of the in geojson coordinates
end_time      | String | End time of the route
end_location  | String | End location of the in geojson coordinates
created_at    | String | The time when the order was created
updated_at    | String | The time when the order was updated

## Retrieve a specific Route

`GET "https://gsmtasks.com/api/tasks/routes/31601953-2355-4192-8505-7c11ba65c53e/"`

## Create Route

Request to create a new route with the parameters provided.

> Example POST request JSON data:

```json
{
  "account": "https://gsmtasks.com/api/tasks/accounts/4368ec5d-9942-4c74-90f7-eea752a6e489/",
  "code": "123ABC",
  "description": "The route I need to take",
  "assignee": "https://gsmtasks.com/api/tasks/users/cfdf3a8e-a9d7-4878-a922-344081a1ed75/",
  "start_time": "2018-01-04T16:39:48+02:00"
}
```

> The request returns JSON of the created Order structured like this:

```json
{
  "id": "31601953-2355-4192-8505-7c11ba65c53e",
  "url": "https://gsmtasks.com/api/tasks/routes/31601953-2355-4192-8505-7c11ba65c53e/",
  "account": "https://gsmtasks.com/api/tasks/accounts/4368ec5d-9942-4c74-90f7-eea752a6e489/",
  "code": "123ABC",
  "description": "The route I need to take",
  "assignee": "https://gsmtasks.com/api/tasks/users/cfdf3a8e-a9d7-4878-a922-344081a1ed75/",
  "start_time": "2018-01-04T16:39:48+02:00",
  "start_location": null,
  "end_time": null,
  "end_location": null,
  "created_at": "2018-01-04T16:39:57.006745+02:00",
  "updated_at": "2018-01-04T16:39:57.006767+02:00"
}
```

`POST https://gsmtasks.com/api/tasks/orders/`

### Request parameters

Parameter     | Type   | Required | Description
------------  | ------ | -------  | -----------
account       | String | Yes      | URL of the account resource
external_id   | String | No       | External id of the order
code          | String | Yes      | Route reference code
description   | String | No       | Description of the route details
assignee      | String | Yes      | URL of the assignee
start_time    | String | Yes      | Start time of the route

## Update Route

Request to update a route.

<aside class="warning">
You can not remove the tasks from the route that have already been completed or cancelled.
</aside>

> Example PUT request JSON data:

```json
{
  "account": "https://gsmtasks.com/api/tasks/accounts/4368ec5d-9942-4c74-90f7-eea752a6e489/",
  "descripion": "Some new description of route details"
}
```

> The request returns JSON of the updated Order structured like this:

```json
{
  "id": "31601953-2355-4192-8505-7c11ba65c53e",
  "url": "https://gsmtasks.com/api/tasks/routes/31601953-2355-4192-8505-7c11ba65c53e/",
  "account": "https://gsmtasks.com/api/tasks/accounts/4368ec5d-9942-4c74-90f7-eea752a6e489/",
  "code": "123ABC",
  "descripion": "Some new description of route details",
  "assignee": "https://gsmtasks.com/api/tasks/users/cfdf3a8e-a9d7-4878-a922-344081a1ed75/",
  "start_time": "2018-01-04T16:39:48+02:00",
  "start_location": null,
  "end_time": null,
  "end_location": null,
  "created_at": "2018-01-04T16:39:57.006745+02:00",
  "updated_at": "2018-01-04T16:39:57.006767+02:00"
}
```

`PUT "https://gsmtasks.com/api/tasks/routes/31601953-2355-4192-8505-7c11ba65c53e/"`

### Request parameters

Parameter     | Type   | Required | Description
------------  | ------ | -------  | -----------
account       | String | Yes      | URL of the account resource
external_id   | String | No       | External id of the order
code          | String | Yes      | Route reference code
description   | String | No       | Description of the route details
assignee      | String | Yes      | URL of the assignee
start_time    | String | Yes      | Start time of the route
