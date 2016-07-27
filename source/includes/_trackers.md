# Trackers

Trackers are sharable tracking links that can be publicly viewed or even embeded on websites trough an iframe.

## List Trackers

Returns a array of trackers that the user has access to.

> The request returns JSON structured like this:

```json
[
  {
      "id": "92133df6-55b7-49f9-9cc3-5a516cee8f52",
      "url": "https://gsmtasks.com/api/tasks/trackers/92133df6-55b7-49f9-9cc3-5a516cee8f52/",
      "account": "https://gsmtasks.com/api/tasks/accounts/4368ec5d-9942-4c74-90f7-eea752a6e489/",
      "tasks": [
          "https://gsmtasks.com/api/tasks/tasks/d09b5fc0-d82f-42ed-9d5f-022d68f36df6/",
          "https://gsmtasks.com/api/tasks/tasks/4c340c01-55eb-4d12-9988-a4a34785b512/"
      ],
      "active_from": "2015-09-08T00:00:00Z",
      "active_until": "2015-09-10T00:00:00Z",
      "active_states": [
          "transit",
          "active"
      ],
      "show_driver_info": true,
      "show_destination": true,
      "show_sms_action": true,
      "show_call_action": true,
      "show_logo": true,
      "show_path": false,
      "autozoom": true,
      "max_zoom_level": null
    }
]
```

`GET https://gsmtasks.com/api/tasks/trackers/`

### Attributes

Attribute        | Type    | Description
---------------- | ------- | -----------
id               | String  | Tracker unique identifier
url              | String  | Unique URL for the resource
account          | String  | URL of the account resource
tasks            | Array   | Tasks that are displayed on this tracker
active_from      | String  | Date and time from when the tracker is active
active_until     | String  | Date and time until when the tracker is active
active_states    | Array   | States of the tasks when the tracker is active
show_driver_info | Boolean | Show driver name
show_destination | Boolean | Show task destination address (only first implemented)
show_sms_action  | Boolean | Show SMS action button
show_call_action | Boolean | Show Call action button
show_logo        | Boolean | Show logo (will be deprecated)
show_path        | Boolean | Show driving path (transit state)
autozoom         | Boolean | Automatic zoom to fallow on the driver
max_zoom_level   | Integer | Maximum Google maps zoom level

## Retrieve a specific Tracker

`GET https://gsmtasks.com/api/tasks/trackers/92133df6-55b7-49f9-9cc3-5a516cee8f52/`

## Create Tracker

Request to create a new tracker with the parameters provided. The tasks that are going to be attached to the tracker need to be created beforehand.

You can read more about creating tasks [here](#tasks).

> Example POST request JSON data:

```json
{
  "account": "https://gsmtasks.com/api/tasks/accounts/4368ec5d-9942-4c74-90f7-eea752a6e489/",
  "tasks": [
      "https://gsmtasks.com/api/tasks/tasks/d09b5fc0-d82f-42ed-9d5f-022d68f36df6/",
      "https://gsmtasks.com/api/tasks/tasks/4c340c01-55eb-4d12-9988-a4a34785b512/"
  ],
  "active_from": "2015-09-08T00:00:00Z",
  "active_until": "2015-09-10T00:00:00Z",
  "active_states": [
      "transit",
      "active"
  ],
  "show_driver_info": true,
  "show_destination": true,
  "show_sms_action": true,
  "show_call_action": true,
  "show_logo": true,
  "show_path": false,
  "autozoom": true,
  "max_zoom_level": null
}
```

> The request returns JSON of the created Order structured like this:

```json
{
  "id": "92133df6-55b7-49f9-9cc3-5a516cee8f52",
  "url": "https://gsmtasks.com/api/tasks/trackers/92133df6-55b7-49f9-9cc3-5a516cee8f52/",
  "account": "https://gsmtasks.com/api/tasks/accounts/4368ec5d-9942-4c74-90f7-eea752a6e489/",
  "tasks": [
      "https://gsmtasks.com/api/tasks/tasks/d09b5fc0-d82f-42ed-9d5f-022d68f36df6/",
      "https://gsmtasks.com/api/tasks/tasks/4c340c01-55eb-4d12-9988-a4a34785b512/"
  ],
  "active_from": "2015-09-08T00:00:00Z",
  "active_until": "2015-09-10T00:00:00Z",
  "active_states": [
      "transit",
      "active"
  ],
  "show_driver_info": true,
  "show_destination": true,
  "show_sms_action": true,
  "show_call_action": true,
  "show_logo": true,
  "show_path": false,
  "autozoom": true,
  "max_zoom_level": null
}
```

`POST https://gsmtasks.com/api/tasks/trackers/`

### Request parameters

Parameter        | Type    | Required | Description
---------------- | ------- | -------  | -----------
account          | String  | Yes      | URL of the account resource
tasks            | Array   | Yes      | Tasks that need to be completed referenced by the URLs
active_from      | String  | Yes      | Date and time from when the tracker is active
active_until     | String  | Yes      | Date and time until when the tracker is active
active_states    | Array   | Yes      | States of the tasks when the tracker is active
show_driver_info | Boolean | Yes      | Show driver name
show_destination | Boolean | Yes      | Show task destination address (only first implemented)
show_sms_action  | Boolean | Yes      | Show SMS action button
show_call_action | Boolean | Yes      | Show Call action button
show_logo        | Boolean | Yes      | Show logo (will be deprecated)
show_path        | Boolean | Yes      | Show driving path (transit state)
autozoom         | Boolean | Yes      | Automatic zoom to fallow on the driver
max_zoom_level   | Integer | Yes      | Maximum Google maps zoom level

## Update Tracker

Request to update a tracker. We will add a task to the tasks array as an example.

> Example PUT request JSON data:

```json
{
  "id": "92133df6-55b7-49f9-9cc3-5a516cee8f52",
  "url": "https://gsmtasks.com/api/tasks/trackers/92133df6-55b7-49f9-9cc3-5a516cee8f52/",
  "account": "https://gsmtasks.com/api/tasks/accounts/4368ec5d-9942-4c74-90f7-eea752a6e489/",
  "tasks": [
      "https://gsmtasks.com/api/tasks/tasks/d09b5fc0-d82f-42ed-9d5f-022d68f36df6/",
      "https://gsmtasks.com/api/tasks/tasks/4c340c01-55eb-4d12-9988-a4a34785b512/"
      "https://gsmtasks.com/api/tasks/tasks/702ef11a-6ee7-44bd-8564-81f9b8a2248f/"
  ],
  "active_from": "2015-09-08T00:00:00Z",
  "active_until": "2015-09-10T00:00:00Z",
  "active_states": [
      "transit",
      "active"
  ],
  "show_driver_info": true,
  "show_destination": true,
  "show_sms_action": true,
  "show_call_action": true,
  "show_logo": true,
  "show_path": false,
  "autozoom": true,
  "max_zoom_level": null
}
```

> The request returns JSON of the updated Order structured like this:

```json
{
  "id": "92133df6-55b7-49f9-9cc3-5a516cee8f52",
  "url": "https://gsmtasks.com/api/tasks/trackers/92133df6-55b7-49f9-9cc3-5a516cee8f52/",
  "account": "https://gsmtasks.com/api/tasks/accounts/4368ec5d-9942-4c74-90f7-eea752a6e489/",
  "tasks": [
      "https://gsmtasks.com/api/tasks/tasks/d09b5fc0-d82f-42ed-9d5f-022d68f36df6/",
      "https://gsmtasks.com/api/tasks/tasks/4c340c01-55eb-4d12-9988-a4a34785b512/"
      "https://gsmtasks.com/api/tasks/tasks/702ef11a-6ee7-44bd-8564-81f9b8a2248f/"
  ],
  "active_from": "2015-09-08T00:00:00Z",
  "active_until": "2015-09-10T00:00:00Z",
  "active_states": [
      "transit",
      "active"
  ],
  "show_driver_info": true,
  "show_destination": true,
  "show_sms_action": true,
  "show_call_action": true,
  "show_logo": true,
  "show_path": false,
  "autozoom": true,
  "max_zoom_level": null
}
```

`POST https://gsmtasks.com/api/tasks/trackers/92133df6-55b7-49f9-9cc3-5a516cee8f52/`
