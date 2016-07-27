# Tasks

All orders consist of tasks. Task is a waypoint that has to be completed in order to full fill the order. There are three categories of tasks - the category is for general reference and also taken into account when tasks are optimized to find the optimal driving route for the driver.

Category    | Description
----------- | -----------
assignment  | Assignment task with no dependencies
pick_up     | Pick up task (dependency - always before drop offs)
drop_off    | Drop off task (dependency - always after pick ups)

### States

Each task has a property state to help you understand the task's most recent status.

State       | Color       | Description
----------- | ----------- | -----------
unassigned  | white       | Task has not yet been assigned to a worker
assigned    | blue        | Task has been assigned to a worker
transit     | purple      | Worker is driving to the location of the task
active      | light green | Worker at location and performing the task
completed   | dark green  | Task has been completed
Failed      | yellow      | Task has failed - waiting to be rescheduled or reattempted
Cancelled   | red         | The task has been cancelled and will not be reattempted

## List Tasks

Returns a array of tasks.

> The request returns JSON structured like this:

```json
[
  {
    "id": "d09b5fc0-d82f-42ed-9d5f-022d68f36df6",
    "url": "https://gsmtasks.com/api/tasks/tasks/d09b5fc0-d82f-42ed-9d5f-022d68f36df6/",
    "account": "https://gsmtasks.com/api/tasks/accounts/4368ec5d-9942-4c74-90f7-eea752a6e489/",
    "external_id": "7869",
    "order": "https://gsmtasks.com/api/tasks/orders/7050443e-4637-4c3a-ade8-1592c308785c/",
    "category": "assignment",
    "reference": "O-112",
    "contact": {
      "name": "Tom ",
      "company": "Smith",
      "phone": "+447700900132",
      "email": "tom.smith@fast.uk",
      "notes": "Call 5 minutes before"
    },
    "address": {
      "raw_address": "Piccadilly Circus, London, United Kingdom",
      "formatted_address": "Piccadilly Circus, London W1D 7ET, UK",
      "location": {
        "type": "Point",
        "coordinates": [
          -0.13457340000002205,
          51.5100974
        ]
      },
      "google_place_id": "ChIJwR8g_9MEdkgR_rI--wzfivA",
      "point_of_interest": "",
      "street": "Piccadilly Circus",
      "house_number": "",
      "apartment_number": "",
      "city": "London",
      "state": "",
      "postal_code": "W1D 7ET",
      "country": "United Kingdom",
      "country_code": "GB"
    },
    "description": "Description of what should the driver do or deliver to that location.",
    "complete_after": "2015-09-08T04:51:36.732219Z",
    "complete_before": null,
    "scheduled_time": null,
    "state": "completed",
    "assignee": "https://gsmtasks.com/api/tasks/users/cfdf3a8e-a9d7-4878-a922-344081a1ed75/",
    "auto_assign": false,
    "duration": "00:15:00",
    "metafields": {},
    "events": "https://gsmtasks.com/api/tasks/tasks/d09b5fc0-d82f-42ed-9d5f-022d68f36df6/events/",
    "documents": "https://gsmtasks.com/api/tasks/tasks/d09b5fc0-d82f-42ed-9d5f-022d68f36df6/documents/",
    "signatures": "https://gsmtasks.com/api/tasks/tasks/d09b5fc0-d82f-42ed-9d5f-022d68f36df6/signatures/"
  }
]
```

`GET https://gsmtasks.com/api/tasks/tasks/`

It's possible to filter the tasks returned by providing the following URL query parameters with the request.

Attribute     |  Description
------------  | -----------
account       | Filter by an account unique identifier
state         | Filter by task state
assignee      | Filter by whom the task has been assigned to
category      | Filter by task category
updated_at    | Filter by updated at
created_at    | Filter by created at

`GET https://gsmtasks.com/api/tasks/tasks/?account=4368ec5d-9942-4c74-90f7-eea752a6e489`

### Attributes

Attribute       | Type    | Description
--------------- | ------- | -----------
id              | String  | Task unique identifier
url             | String  | Unique URL for the resource
account         | String  | URL of the account resource
external_id     | String  | Unique identifier of an external system for ease of integration
order           | String  | URL of the order resource
category        | String  | Category of the task (pickup, drop_off, ...)
reference       | String  | Order reference number
contact         | Object  | Contact object describing the contact person for that task
address         | Object  | Address object describing the location of the task
description     | String  | Description of the task
complete_after  | String  | Sets the time after what the task should be completed (if not defined it will default to creation time)
complete_before | String  | Sets the time before what the task should be completed
scheduled_time  | String  | The time scheduled by the worker from the mobile app
state           | String  | Show the current state of the task
assignee        | String  | URL of the user resource the task has been assigned to
auto_assign     | Boolean | Should the task be auto assigned to the best suited driver
duration        | String  | Duration planned for the completion of the task at location
metafields      | Object  | Metafields contain custom datafields that have been configured
events          | String  | URL to fetch all the task related events
documents       | String  | URL to fetch all the task related documents
signatures      | String  | URL to fetch all the task related signatures

## Retrieve a specific Task

`GET https://gsmtasks.com/api/tasks/task/d09b5fc0-d82f-42ed-9d5f-022d68f36df6/`


## Create Task

Request to create a new task with the parameters provided

> Example POST request JSON data:

```json
{
  "account": "https://gsmtasks.com/api/tasks/accounts/4368ec5d-9942-4c74-90f7-eea752a6e489/",
  "external_id": "7869",
  "order": "https://gsmtasks.com/api/tasks/orders/7050443e-4637-4c3a-ade8-1592c308785c/",
  "category": "assignment",
  "reference": "O-112",
  "contact": {
    "name": "Tom ",
    "company": "Smith",
    "phone": "+447700900132",
    "email": "tom.smith@fast.uk",
    "notes": "Call 5 minutes before"
  },
  "address": {
    "raw_address": "Piccadilly Circus, London, United Kingdom"
  },
  "description": "Description of what should the driver do or deliver to that location.",
  "complete_after": "2015-09-08T10:00:00Z",
  "complete_before": "2015-09-08T11:00:00Z",
  "assignee": "https://gsmtasks.com/api/tasks/users/cfdf3a8e-a9d7-4878-a922-344081a1ed75/",
  "auto_assign": false
}
```

> The request returns JSON of the created Task structured like this:

```json
{
  "id": "d09b5fc0-d82f-42ed-9d5f-022d68f36df6",
  "url": "https://gsmtasks.com/api/tasks/tasks/d09b5fc0-d82f-42ed-9d5f-022d68f36df6/",
  "account": "https://gsmtasks.com/api/tasks/accounts/4368ec5d-9942-4c74-90f7-eea752a6e489/",
  "external_id": "7869",
  "order": "https://gsmtasks.com/api/tasks/orders/7050443e-4637-4c3a-ade8-1592c308785c/",
  "category": "assignment",
  "reference": "O-112",
  "contact": {
    "name": "Tom ",
    "company": "Smith",
    "phone": "+447700900132",
    "email": "tom.smith@fast.uk",
    "notes": "Call 5 minutes before"
  },
  "address": {
    "raw_address": "Piccadilly Circus, London, United Kingdom",
    "formatted_address": "Piccadilly Circus, London W1D 7ET, UK",
    "location": {
      "type": "Point",
      "coordinates": [
        -0.13457340000002205,
        51.5100974
      ]
    },
    "google_place_id": "ChIJwR8g_9MEdkgR_rI--wzfivA",
    "point_of_interest": "",
    "street": "Piccadilly Circus",
    "house_number": "",
    "apartment_number": "",
    "city": "London",
    "state": "",
    "postal_code": "W1D 7ET",
    "country": "United Kingdom",
    "country_code": "GB"
  },
  "description": "Description of what should the driver do or deliver to that location.",
  "complete_after": "2015-09-08T04:51:36.732219Z",
  "complete_before": null,
  "scheduled_time": null,
  "state": "completed",
  "assignee": "https://gsmtasks.com/api/tasks/users/cfdf3a8e-a9d7-4878-a922-344081a1ed75/",
  "auto_assign": false,
  "duration": "00:15:00",
  "metafields": {},
  "events": "https://gsmtasks.com/api/tasks/tasks/d09b5fc0-d82f-42ed-9d5f-022d68f36df6/events/",
  "documents": "https://gsmtasks.com/api/tasks/tasks/d09b5fc0-d82f-42ed-9d5f-022d68f36df6/documents/",
  "signatures": "https://gsmtasks.com/api/tasks/tasks/d09b5fc0-d82f-42ed-9d5f-022d68f36df6/signatures/"
}
```

`POST https://gsmtasks.com/api/tasks/tasks/`

### Request parameters

Parameter       | Type    | Required | Description
--------------- | ------- | -------- | -----------
account         | String  | Yes      | URL of the account resource
external_id     | String  | No       | Unique identifier of an external system for ease of integration
reference       | String  | No       | Order reference number
category        | String  | Yes      | Category of the task (pickup, drop_off, ...)
contact         | Object  | No       | Contact object describing the contact person for that task
address         | Object  | Yes      | Address object describing the location of the task
description     | String  | No       | Description of the task
complete_after  | String  | No       | Sets the time after what the task should be completed (if not defined it will default to creation time)
complete_before | String  | No       | Sets the time before what the task should be completed
assignee        | String  | No       | URL of the user resource the task has been assigned to
auto_assign     | Boolean | No       | Should the task be auto assigned to the best suited driver
duration        | String  | No       | Duration planned for the completion of the task at location
metafields      | Object  | No       | Metafields contain custom datafields that have been configured

### Using serialized objects instead of URLs

For the assignee field, it is possible to create a task using a short serialized representation of the user object instead of the user's hyperlink. The user will be looked up on the server side using the provided e-mail address.

```json
{
  "account": "https://gsmtasks.com/api/tasks/accounts/4368ec5d-9942-4c74-90f7-eea752a6e489/",
  "address": {
    "raw_address": "Piccadilly Circus, London, United Kingdom"
  },
  "assignee": {
    "email": "worker@mycompany.com"
  }
}
```
