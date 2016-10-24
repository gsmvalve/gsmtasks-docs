# Task Address Feature

## List Task Address Feature

Returns a array of task address feature that the user has access to.

> The request returns JSON structured like this:

```json
{
    "type": "FeatureCollection",
    "features": [
        {
            "id": "d09b5fc0-d82f-42ed-9d5f-022d68f36df6",
            "type": "Feature",
            "geometry": {
                "type": "Point",
                "coordinates": [
                    24.716517899999985,
                    59.4329769
                ]
            },
            "properties": {
                "model": "task_address_feature",
                "task": "https://gsmtasks.com/api/tasks/tasks/d09b5fc0-d82f-42ed-9d5f-022d68f36df6/",
                "formatted_address": "Paldiski maantee 42d, 10612 Tallinn, Estonia",
                "category": "assignment",
                "state": "completed"
            }
        }
    ]
}
```

`GET https://gsmtasks.com/api/tasks/task_address_features/`

### Attributes

Attribute     | Type   | Description
------------  | ------ | -----------
id            | String | Task event track unique identifier
type          | String | Type of the task event track
geometry      |        |
properties    |        |
