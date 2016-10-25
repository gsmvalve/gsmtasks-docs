# Time Locations

## List Time Locations

Returns a array of time locations that the user has access to.

> The request returns JSON structured like this:

```json
[
    {
        "id": "78d0c5d7-974c-415d-a884-7458aa1e5a5f",
        "url": "https://gsmtasks.com/api/tasks/time_locations/78d0c5d7-974c-415d-a884-7458aa1e5a5f/",
        "user": "https://gsmtasks.com/api/tasks/users/04a01121-c95c-40d5-9910-d55c803533bb/",
        "time": "2016-03-04T06:28:52.926000Z",
        "location": {
            "type": "Point",
            "coordinates": [
                24.7294207,
                59.4398418
            ]
        },
        "registration": "",
        "state": "unknown",
        "heading": 0,
        "speed": 0,
        "altitude": 0,
        "accuracy": 30,
        "battery_level": "0.980",
        "created_at": "2016-10-19T13:01:15.456895Z",
        "updated_at": "2016-10-19T13:01:15.456956Z"
    }
]
```

`GET https://gsmtasks.com/api/tasks/time_locations/`

### Attributes

Attribute     | Type   | Description
------------  | ------ | -----------
id            | String | Time location unique identifier
url           | String | Unique URL for the resource
user          | String | URL of the user who created time location
time          | String |
location      | Object | A GEOJSON object ????
registration  | String |
state         | String | Unknown, stopped or moving.
heading       | Integer|
speed         | Integer|
altitude      | Integer|
accuracy      | Integer|
battery_level |        |
created_at    | String | The time when the order was created
updated_at    | String | The time when the order was updated

## Retrieve a specific Time Location

`GET https://gsmtasks.com/api/tasks/time_locations/78d0c5d7-974c-415d-a884-7458aa1e5a5f/`

## Create Time Location

Request to create a new time location with the parameters provided. 

> Example POST request JSON data:

```json
{
    "time": "2016-01-14T14:33:00Z",
    "location": {
        "type": "Point",
        "coordinates": [
            24.7297895322,
            59.439981842
        ]
    },
    "registration": "123AAA",
    "state": "stopped",
    "heading": null,
    "speed": null,
    "altitude": null,
    "accuracy": null,
    "battery_level": null
}
```

> The request returns JSON of the created Order structured like this:

```json
{
    "id": "dea56300-382d-4a0b-8424-cbc6e1941bbb",
    "url": "http://127.0.0.1:8000/api/tasks/time_locations/dea56300-382d-4a0b-8424-cbc6e1941bbb/",
    "user": "http://127.0.0.1:8000/api/tasks/users/adba000d-9f1b-4469-a2b7-7dfb7977f57b/",
    "time": "2016-01-14T14:33:00Z",
    "location": {
        "type": "Point",
        "coordinates": [
            24.7297895322,
            59.439981842
        ]
    },
    "registration": "123AAA",
    "state": "stopped",
    "heading": null,
    "speed": null,
    "altitude": null,
    "accuracy": null,
    "battery_level": null,
    "created_at": "2016-10-25T07:59:18.510722Z",
    "updated_at": "2016-10-25T07:59:18.510795Z"
}
```

`POST https://gsmtasks.com/api/tasks/time_locations/`

### Request parameters

Attribute     | Type   | Required | Description
------------  | ------ | -------- | -----------
time          | String | Yes      |
location      | Object | Yes      | A GEOJSON object ????
registration  | String | No       |
state         | String | Yes      | Unknown, stopped or moving.
heading       | Integer| No       |
speed         | Integer| No       |
altitude      | Integer| No       |
accuracy      | Integer| No       |
battery_level |        | No       |
