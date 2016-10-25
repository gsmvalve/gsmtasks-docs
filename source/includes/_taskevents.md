# Task Events

A task event object is a definition of user action against one particular task. As there are many task events for each task a task event history is formed.

It's also possible to define a callback to the clients server about the task event so it's possible to update the task states also in the CRM or any other system that for example needs to know when a task was completed.

The following task events are registered and sent.

State       | Description
----------- | -----------
created     | Task has been created
assign      | Task has been assigned to a worker
unassign    | Task has been unassigned
transit     | Task has gone into transit mode
active      | Task has been activated
completed   | Task has been completed
Failed      | Task has failed
Cancelled   | The task has been cancelled

<aside class="notice">
To configure the Task Events callback please contact [info@gsmtasks.com](mailto:info@gsmtasks.com)
</aside>

## List Task Events

Returns a array of accounts that the user has access to.

> The request returns JSON structured like this:

```json
[
  {
    "id": "d9a80a68-bf33-488b-9f8f-3da038aadea8",
    "url": "https://gsmtasks.com/api/tasks/task_events/d9a80a68-bf33-488b-9f8f-3da038aadea8/",
    "task": "https://gsmtasks.com/api/tasks/tasks/46267d9f-66cd-4fdb-9e9e-aaa63c81f29b/",
    "field": "state",
    "event": "activate",
    "from_state": "transit",
    "to_state": "active",
    "user": "https://gsmtasks.com/api/tasks/users/2e25e0c6-889c-4eda-ae3c-db27949fa05d/",
    "notes": "",
    "location": {
      "type": "Point",
      "coordinates": [
        -0.13457340000002205,
        51.5100974
      ]
    },
    "assignee": "https://gsmtasks.com/api/tasks/users/2e25e0c6-889c-4eda-ae3c-db27949fa05d/",
    "created_at": "2016-05-10T09:07:28.172058Z",
    "updated_at": "2016-05-10T09:07:39.294848Z"
  }
]
```

`GET https://gsmtasks.com/api/tasks/task_events/`

### Attributes

Attribute     | Type   | Description
------------  | ------ | -----------
id            | String | Task Event unique identifier
url           | String | Unique URL for the resource
task          | String | URL of the task resource
field         | String | ????
event         | String | Event name
from_state    | String | The state from where the event was triggered
to_state      | String | The state to which the task was transitioned to
user          | String | URL of the user who triggered the event
notes         | String | Any comments / notes attached to the event
location      | Object | A GeoJSON object that defines the location from where the task was triggered from
assignee      | String | URL of the user who the task was assigned to
created_at    | String | The time when the task event was created
updated_at    | String | The time when the task event was updated

## Retrieve a specific Task Event

`GET https://gsmtasks.com/api/tasks/task_events/d9a80a68-bf33-488b-9f8f-3da038aadea8/`
