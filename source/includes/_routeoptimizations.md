# Route Optimizations

Route optimizations are triggered to find the optimal driving route to complete the tasks given.

<aside class="notice">
Route optimizations allow a maximum of 80 tasks to be optimized at once.
</aside>

### States

Each route optimization has a state. Route optimizations are queued so they are executed async.

State       | Description
----------- | -----------
pending     | Route optimization has just been created and queued
started     | Route optimization in progress
completed   | Route optimization completed and tasks reordered
failed      | Route optimization failed

<aside class="success">
Once the Route optimization has reached the <i>completed</i> state - the task positions have been reordered in the tasks endpoint.
</aside>

## List Route Optimizations

Returns a array of route optimizations that the user has access to.

> The request returns JSON structured like this:

```json
[
  {
    "id": "ae0fbdc6-f4b9-4c0b-91e9-b15d333ed28d",
    "url": "https://gsmtasks.com/api/tasks/route_optimizations/ae0fbdc6-f4b9-4c0b-91e9-b15d333ed28d/",
    "account": "https://gsmtasks.com/api/tasks/accounts/4368ec5d-9942-4c74-90f7-eea752a6e489/",
    "assignee": "https://gsmtasks.com/api/tasks/users/12d2821e-01e2-48fb-97bc-eaebca93cbdc/",
    "state": "completed",
    "tasks": [
        "https://gsmtasks.com/api/tasks/tasks/d09b5fc0-d82f-42ed-9d5f-022d68f36df6/",
        "https://gsmtasks.com/api/tasks/tasks/2ab15703-6c4c-48db-b305-88c117b763db/",
        "https://gsmtasks.com/api/tasks/tasks/d6ed4d74-9a38-429c-ba1c-f9e073461ad7/"
    ],
    "start_location": null,
    "end_location": null,
    "total_distance": null,
    "total_duration": null,
    "created_at": "2016-10-10T13:26:33.979847Z",
    "updated_at": "2016-10-10T13:26:33.979877Z"
  }
]
```

`GET https://gsmtasks.com/api/tasks/route_optimizations/`

### Attributes

Attribute      | Type   | Description
-------------- | ------ | -----------
id             | String | Route optimization unique identifier
url            | String | Unique URL for the resource
account        | String | URL of the account resource
assignee       | String | URL of the user resource
tasks          | Array  | URLs of the task resources to be optimized
start_location | String | Starting location
end_location   | String | Ending location
total_distance | String | Distance of the optimized route
total_duration | String | Duration of the optimized route
created_at     | String  | The time when the route optimization  was created
updated_at     | String | The time when the route optimization was updated

## Retrieve a specific Route optimization

`GET https://gsmtasks.com/api/tasks/route_optimizations/4368ec5d-9942-4c74-90f7-eea752a6e489/`

## Create Route optimization

Request to create a new route optimization with the parameters provided

> Example POST request JSON data:

```json
{
  "account": "https://gsmtasks.com/api/tasks/accounts/4368ec5d-9942-4c74-90f7-eea752a6e489/",
  "assignee": "https://gsmtasks.com/api/tasks/users/12d2821e-01e2-48fb-97bc-eaebca93cbdc/",
  "tasks": [
      "https://gsmtasks.com/api/tasks/tasks/d09b5fc0-d82f-42ed-9d5f-022d68f36df6/",
      "https://gsmtasks.com/api/tasks/tasks/2ab15703-6c4c-48db-b305-88c117b763db/",
      "https://gsmtasks.com/api/tasks/tasks/d6ed4d74-9a38-429c-ba1c-f9e073461ad7/"
  ]
}
```

> The request returns JSON of the created Account structured like this:

```json
{
  "id": "ae0fbdc6-f4b9-4c0b-91e9-b15d333ed28d",
  "url": "https://gsmtasks.com/api/tasks/route_optimizations/ae0fbdc6-f4b9-4c0b-91e9-b15d333ed28d/",
  "account": "https://gsmtasks.com/api/tasks/accounts/4368ec5d-9942-4c74-90f7-eea752a6e489/",
  "assignee": "https://gsmtasks.com/api/tasks/users/12d2821e-01e2-48fb-97bc-eaebca93cbdc/",
  "state": "completed",
  "tasks": [
      "https://gsmtasks.com/api/tasks/tasks/d09b5fc0-d82f-42ed-9d5f-022d68f36df6/",
      "https://gsmtasks.com/api/tasks/tasks/2ab15703-6c4c-48db-b305-88c117b763db/",
      "https://gsmtasks.com/api/tasks/tasks/d6ed4d74-9a38-429c-ba1c-f9e073461ad7/"
  ],
  "start_location": null,
  "end_location": null,
  "total_distance": null,
  "total_duration": null,
  "created_at": "2016-10-10T13:26:33.979847Z",
  "updated_at": "2016-10-10T13:26:33.979877Z"
}
```

`POST https://gsmtasks.com/api/tasks/route_optimizations/`

### Request parameters

Parameter     | Type   | Required | Description
------------  | ------ | -------  | -----------
account       | String | Yes      | URL of the account resource
assignee      | String | Yes      | URL of the user resource
tasks         | Array  | Yes      | URLs of the task resources to be optimized
