# Notifications

recipient   | Description
----------- | -----------
account     | 
asignee     | 
orderer     | 
receiver    | 
contact     | 
client      | 

## List Notifications

Returns a array of notifications that the user has access to.

> The request returns JSON structured like this:

```json
[
    {
        "id": "5bb47214-66a1-4f1e-9e00-ee287e3648ec",
        "url": "https://gsmtasks.com/api/tasks/notifications/5bb47214-66a1-4f1e-9e00-ee287e3648ec/",
        "task": "https://gsmtasks.com/api/tasks/tasks/90c65c5e-b8b8-44c9-9d8b-cb7f91b53c38/",
        "event": "create",
        "recipient": "account",
        "emails": [
            "tom.smith@fast.uk"
        ],
        "phone": "+447700900132",
        "app": false,
        "message": "Example message",
        "created_at": "2016-10-24T10:45:26.599735Z",
        "updated_at": "2016-10-24T10:45:26.599764Z"
    }
]
```

`GET https://gsmtasks.com/api/tasks/notifications/`

### Attributes

Attribute     | Type   | Description
------------  | ------ | -----------
id            | String | notification unique identifier
url           | String | Unique URL for the resource
task          | String | URL of the task resource
event         | String | ?????????
recipient     | String | Task event choices ???????
emails        | Array  | 
phone         | String |      
app           | Boolean|
message       | String |      
created_at    | String | The time when the notification was created
updated_at    | String | The time when the notification was updated

## Retrieve a specific Notification

`GET https://gsmtasks.com/api/tasks/notifications/5bb47214-66a1-4f1e-9e00-ee287e3648ec/`

## Create Notifiation

Request to create a new Notification with the parameters provided.

> Example POST request JSON data:

```json
{
    "task": "https://gsmtasks.com/api/tasks/tasks/90c65c5e-b8b8-44c9-9d8b-cb7f91b53c38/",
    "event": "create",
    "recipient": "account",
    "emails": [
        "tom.smith@fast.uk"
    ],
    "phone": "+447700900132",
    "app": false,
    "message": "Example message"
}
```

> The request returns JSON of the created Order structured like this:

```json
{
    "id": "5bb47214-66a1-4f1e-9e00-ee287e3648ec",
    "url": "https://gsmtasks.com/api/tasks/notifications/5bb47214-66a1-4f1e-9e00-ee287e3648ec/",
    "task": "https://gsmtasks.com/api/tasks/tasks/90c65c5e-b8b8-44c9-9d8b-cb7f91b53c38/",
    "event": "create",
    "recipient": "account",
    "emails": [
        "tom.smith@fast.uk"
    ],
    "phone": "+447700900132",
    "app": false,
    "message": "Example message",
    "created_at": "2016-10-24T10:45:26.599735Z",
    "updated_at": "2016-10-24T10:45:26.599764Z"
}
```

`POST https://gsmtasks.com/api/tasks/notifications/`

### Request parameters

Parameter     | Type   | Required | Description
------------  | ------ | -------  | -----------
task          | String | Yes      | URL of the task resource
event         | String | No       | Task event state choices ?????
recipient     | String | No       | 
emails        | Array  | No       |            
phone         | String | No       |   
app           | Boolean| No       |      
message       | String | Yes      |        