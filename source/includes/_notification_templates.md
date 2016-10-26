# Notification Templates

## List Notification Templates

Returns a array of notification templates that the user has access to.

> The request returns JSON structured like this:

```json
[
    {
        "id": "8eaa96d6-e4b7-4592-ace9-aa05576c868d",
        "url": "https://gsmtasks.com/api/tasks/notification_templates/8eaa96d6-e4b7-4592-ace9-aa05576c868d/",
        "account": "https://gsmtasks.com/api/tasks/accounts/798d8fda-43d1-497a-b63b-1ad784afc117/",
        "name": "Name",
        "event": "",
        "recipient": "account",
        "via_sms": true,
        "via_email": false,
        "via_app": false,
        "is_active": false,
        "message": "message",
        "created_at": "2016-10-10T11:34:31.497853Z",
        "updated_at": "2016-10-25T07:01:13.009925Z"
    }
]
```

`GET https://gsmtasks.com/api/tasks/notification_templates/`

### Attributes

Attribute     | Type   | Description
------------  | ------ | -----------
id            | String | Notificaton template unique identifier
url           | String | Unique URL for the resource
account       | String | URL of the account resource
name          | String | Name of the notification template
event         | String | 
recipient     | String |
via_sms       | Boolean| 
via_email     | Boolean|
via_app       | Boolean|
is_active     | Boolean|
message       | String | 
created_at    | String | The time when the notification template was created
updated_at    | String | The time when the notification template was updated

## Retrieve a specific Notification Template

`GET https://gsmtasks.com/api/tasks/notification_templates/8eaa96d6-e4b7-4592-ace9-aa05576c868d/`

## Create Notification Template

> Example POST request JSON data:

```json
{
    "account": "https://gsmtasks.com/api/tasks/accounts/798d8fda-43d1-497a-b63b-1ad784afc117/",
    "name": "Name",
    "event": "create",
    "recipient": "account",
    "via_sms": true,
    "via_email": false,
    "via_app": false,
    "is_active": false,
    "message": "message"
}
```

> The request returns JSON of the created Notification Template structured like this:

```json
{
    "id": "773ef894-290d-4ab7-ab40-c53eaa47237f",
    "url": "https://gsmtasks.com/api/tasks/notification_templates/773ef894-290d-4ab7-ab40-c53eaa47237f/",
    "account": "https://gsmtasks.com/api/tasks/accounts/798d8fda-43d1-497a-b63b-1ad784afc117/",
    "name": "Name",
    "event": "create",
    "recipient": "account",
    "via_sms": true,
    "via_email": false,
    "via_app": false,
    "is_active": false,
    "message": "message",
    "created_at": "2016-10-25T07:18:33.672215Z",
    "updated_at": "2016-10-25T07:18:33.672239Z"
}
```

`POST https://gsmtasks.com/api/tasks/notification_templates/`

### Request parameters

Parameter     | Type   | Required | Description
------------  | ------ | -------- | -----------
account       | String | Yes      | URL of the account resource
name          | String | Yes      | Name of the notification template
event         | String | Yes      | 
recipient     | String | Yes      |
via_sms       | Boolean| No       | 
via_email     | Boolean| No       |
via_app       | Boolean| No       |
is_active     | Boolean| No       |
message       | String | Yes      |
 
## Update Notification Template

Request to update a notification template. We will change the name, via_sms status and via_email status as an example.

> Example PUT request JSON data:

```json
{
    "account": "https://gsmtasks.com/api/tasks/accounts/798d8fda-43d1-497a-b63b-1ad784afc117/",
    "name": "Notification template",
    "via_sms": false,
    "via_email": true,
    "message": "important"
}
```

> The request returns JSON of the updated Order structured like this:

```json
{
    "id": "773ef894-290d-4ab7-ab40-c53eaa47237f",
    "url": "https://gsmtasks.com/api/tasks/notification_templates/773ef894-290d-4ab7-ab40-c53eaa47237f/",
    "account": "https://gsmtasks.com/api/tasks/accounts/798d8fda-43d1-497a-b63b-1ad784afc117/",
    "name": "Notification template",
    "event": "create",
    "recipient": "account",
    "via_sms": false,
    "via_email": true,
    "via_app": false,
    "is_active": false,
    "message": "important",
    "created_at": "2016-10-25T07:18:33.672215Z",
    "updated_at": "2016-10-25T07:27:59.460450Z"
}
```

`PUT https://gsmtasks.com/api/tasks/notification_templates/773ef894-290d-4ab7-ab40-c53eaa47237f/`

### Request parameters

Parameter     | Type   | Required | Description
------------  | ------ | -------- | -----------
account       | String | Yes      | URL of the account resource
name          | String | Yes      | Name of the notification template
event         | String | No       | 
recipient     | String | No       |
via_sms       | Boolean| No       | 
via_email     | Boolean| No       |
via_app       | Boolean| No       |
is_active     | Boolean| No       |
message       | String | Yes      |
 


