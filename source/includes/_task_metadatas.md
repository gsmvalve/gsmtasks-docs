# Task Metadatas

## List Task Metadatas

Returns a array of task metadatas that the user has access to.

> The request returns JSON structured like this:

```json
[
    {
        "id": "eed4a5fe-5cde-4859-baaf-68b60b2c03af",
        "url": "https://gsmtasks.com/api/tasks/task_metadatas/eed4a5fe-5cde-4859-baaf-68b60b2c03af/",
        "task": "https://gsmtasks.com/api/tasks/tasks/008110f2-8e66-4b17-b9b3-73da42c1e8f8/",
        "events_count": 5,
        "documents_count": 0,
        "signatures_count": 0,
        "forms_count": 0,
        "forms_completed_count": 0,
        "unassigned_duration": "00:00:00.007993",
        "assigned_duration": "00:30:38.002657",
        "accepted_duration": "00:00:00",
        "transit_duration": "75 22:49:15.261130",
        "active_duration": "00:00:00",
        "completed_duration": "00:00:00",
        "failed_duration": "00:00:00",
        "cancelled_duration": "00:00:00",
        "last_unassigned_at": null,
        "last_assigned_at": null,
        "last_accepted_at": null,
        "last_transit_at": null,
        "last_active_at": null,
        "last_completed_at": null,
        "last_failed_at": null,
        "last_cancelled_at": null
    }
]
```

`GET https://gsmtasks.com/api/tasks/task_metadatas/`

### Attributes

Attribute                | Type   | Description
------------------------ | ------ | -----------
id                       | String | Task metadata unique identifier
url                      | String | Unique URL for the resource
task                     | String | URL of the task resource
events_count             | Integer|
documents_count          | Integer| 
signatures_count         | Integer|
forms_count              | Integer|
forms_completed_count    | Integer|
unassigned_duration      | String |
assigned_duration        | String |
accepted_duration        | String |            
transit_duration         | String |
active_duration          | String |      
completed_duration       | String |
failed_duration          | String |               
cancelled_duration       | String |
last_unassigned_at       | String |              
last_assigned_at         | String |
last_accepted_at         | String |                   
last_transit_at          | String |
last_active_at           | String |            
last_completed_at        | String |
last_failed_at           | String |           
last_cancelled_at        | String |

## Retrieve a specific Task metadata

`GET https://gsmtasks.com/api/tasks/task_metadatas/eed4a5fe-5cde-4859-baaf-68b60b2c03af/`