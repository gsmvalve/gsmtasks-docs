# Task Forms

## List Task Forms

Returns a array of task forms that the user has access to.

```json
[
    {
        "id": "9d361905-6871-489e-89b8-a218178c6faa",
        "url": "https://gsmtasks.com/api/tasks/task_forms/9d361905-6871-489e-89b8-a218178c6faa/",
        "task": "https://gsmtasks.com/api/tasks/tasks/90c65c5e-b8b8-44c9-9d8b-cb7f91b53c38/",
        "name": "Name",
        "link": "https://gsmtasks.com/api/tasks/tasks/90c65c5e-b8b8-44c9-9d8b-cb7f91b53c38/",
        "edit_url": "https://gsmtasks.com/api/tasks/tasks/90c65c5e-b8b8-44c9-9d8b-cb7f91b53c38/",
        "view_url": "https://gsmtasks.com/api/tasks/tasks/90c65c5e-b8b8-44c9-9d8b-cb7f91b53c38/",
        "pdf_url": "https://gsmtasks.com/api/tasks/tasks/90c65c5e-b8b8-44c9-9d8b-cb7f91b53c38/",
        "completed": false,
        "created_at": "2016-10-07T11:12:01.237733Z",
        "updated_at": "2016-10-07T11:12:01.237761Z"
    }
]
```

`GET https://gsmtasks.com/api/tasks/task_forms/`

### Attributes

Attribute    | Type   | Description
------------ | ------ | -----------
id           | String | Task form unique identifier
url          | String | Unique URL for the resource
task         | String | URL of the task resource
name         | String | Name of the task form
link         | String | 
edit_url     | String | 
view_url     | String | 
pdf_url      | String | 
completed    | Boolean| Shows whether the task form is completed or not
created_at   | String | The time when the task form was created
updated_at   | String | The time when the task form was updated

## Retrieve a specific Task form

`GET https://gsmtasks.com/api/tasks/task_forms/9d361905-6871-489e-89b8-a218178c6faa/`

## Create Task form

Request to create a new task form with the parameters provided. The tasks that are going to be attached to the task form need to be created beforehand.

You can read more about creating tasks [here](#tasks).

> Example POST request JSON data:

```json
{
    "task": "https://gsmtasks.com/api/tasks/tasks/90c65c5e-b8b8-44c9-9d8b-cb7f91b53c38/",
    "name": "Name",
    "edit_url": "https://gsmtasks.com/api/tasks/tasks/90c65c5e-b8b8-44c9-9d8b-cb7f91b53c38/",
    "view_url": "https://gsmtasks.com/api/tasks/tasks/90c65c5e-b8b8-44c9-9d8b-cb7f91b53c38/",
    "pdf_url": "https://gsmtasks.com/api/tasks/tasks/90c65c5e-b8b8-44c9-9d8b-cb7f91b53c38/",
    "completed": false
}
```

> The request returns JSON of the created Order structured like this:

```json
{
    "id": "9d361905-6871-489e-89b8-a218178c6faa",
    "url": "https://gsmtasks.com/api/tasks/task_forms/9d361905-6871-489e-89b8-a218178c6faa/",
    "task": "https://gsmtasks.com/api/tasks/tasks/90c65c5e-b8b8-44c9-9d8b-cb7f91b53c38/",
    "name": "Name",
    "link": "https://gsmtasks.com/api/tasks/tasks/90c65c5e-b8b8-44c9-9d8b-cb7f91b53c38/",
    "edit_url": "https://gsmtasks.com/api/tasks/tasks/90c65c5e-b8b8-44c9-9d8b-cb7f91b53c38/",
    "view_url": "https://gsmtasks.com/api/tasks/tasks/90c65c5e-b8b8-44c9-9d8b-cb7f91b53c38/",
    "pdf_url": "https://gsmtasks.com/api/tasks/tasks/90c65c5e-b8b8-44c9-9d8b-cb7f91b53c38/",
    "completed": false,
    "created_at": "2016-10-07T11:12:01.237733Z",
    "updated_at": "2016-10-07T11:12:01.237761Z"
}
```

`POST https://gsmtasks.com/api/tasks/task_forms/`

### Request parameters

Parameter     | Type   | Required | Description
------------  | ------ | -------  | -----------
task          | String | Yes      | URL of the account resource
name          | String | Yes      | Name of the task form
edit_url      | String | Yes      |
view_url      | String | No       | 
pdf_url       | String | No       | 
completed     | Boolean| No       | Shows whether the task form is completed or not

## Update Task Form

Request to update a Task Form. We will change the name and the completed status as an example.

> Example PUT request JSON data:

```json
{
    "task": "https://gsmtasks.com/api/tasks/tasks/90c65c5e-b8b8-44c9-9d8b-cb7f91b53c38/",
    "name": "Some other name",
    "edit_url": "https://gsmtasks.com/api/tasks/tasks/90c65c5e-b8b8-44c9-9d8b-cb7f91b53c38/",
    "completed": true
}
```

> The request returns JSON of the updated Order structured like this:

```json
{
    "id": "9d361905-6871-489e-89b8-a218178c6faa",
    "url": "https://gsmtasks.com/api/tasks/task_forms/9d361905-6871-489e-89b8-a218178c6faa/",
    "task": "https://gsmtasks.com/api/tasks/tasks/90c65c5e-b8b8-44c9-9d8b-cb7f91b53c38/",
    "name": "Some other name",
    "link": "https://gsmtasks.com/api/tasks/tasks/90c65c5e-b8b8-44c9-9d8b-cb7f91b53c38/",
    "edit_url": "https://gsmtasks.com/api/tasks/tasks/90c65c5e-b8b8-44c9-9d8b-cb7f91b53c38/",
    "view_url": "https://gsmtasks.com/api/tasks/tasks/90c65c5e-b8b8-44c9-9d8b-cb7f91b53c38/",
    "pdf_url": "https://gsmtasks.com/api/tasks/tasks/90c65c5e-b8b8-44c9-9d8b-cb7f91b53c38/",
    "completed": true,
    "created_at": "2016-10-07T11:12:01.237733Z",
    "updated_at": "2016-10-07T11:12:01.237761Z"
}
```

`PUT https://gsmtasks.com/api/tasks/task_forms/9d361905-6871-489e-89b8-a218178c6faa/`

### Request parameters

Parameter     | Type   | Required | Description
------------  | ------ | -------  | -----------
task          | String | Yes      | URL of the account resource
name          | String | Yes      | Name of the task form
edit_url      | String | Yes      |
view_url      | String | No       | 
pdf_url       | String | No       | 
completed     | Boolean| No       | Shows whether the task form is completed or not