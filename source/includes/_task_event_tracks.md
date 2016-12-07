# Task Event Tracks

## List Task Event Tracks

Returns a array of task event tracks that the user has access to.

> The request returns JSON structured like this:

```json
{
    "type": "FeatureCollection",
    "features": [
        {
            "id": "d1dba784-f973-42f0-a875-7889676e077e",
            "type": "Feature",
            "geometry": {
                "type": "LineString",
                "coordinates": [
                    [
                        24.7773089,
                        59.4289815
                    ],
                    [
                        24.7297235,
                        59.4403178
                    ]
                ]
            },
            "properties": {
                "model": "task_event_track",
                "url": "https://gsmtasks.com/api/tasks/task_event_tracks/d1dba784-f973-42f0-a875-7889676e077e/",
                "task": "ffec72b7-8e5a-4062-b338-33fa458a497b",
                "task_event": "https://gsmtasks.com/api/tasks/task_events/d1dba784-f973-42f0-a875-7889676e077e/",
                "event": "unaccept",
                "from_state": "accepted",
                "to_state": "assigned",
                "user": "cfdf3a8e-a9d7-4878-a922-344081a1ed75",
                "notes": "",
                "assignee": "cfdf3a8e-a9d7-4878-a922-344081a1ed75",
                "created_at": "2016-10-24T05:17:39.459316Z",
                "updated_at": "2016-10-24T05:17:50.948596Z"
            }
        }
    ]
}
```

`GET https://gsmtasks.com/api/tasks/task_event_tracks/`

### Attributes

Attribute     | Type   | Description
------------  | ------ | -----------
id            | String | Task event track unique identifier
type          | String | Type of the task event track
geometry      | object | 
properties    | object | 
