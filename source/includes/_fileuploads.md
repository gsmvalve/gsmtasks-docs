# File uploads

To attach a file to a Task or Order. The file has to be uploaded via this endpoint.

## List File Uploads

Returns a array of file uploads that the user has access to.

> The request returns JSON structured like this:

```json
[
  {
        "id": "24588f76-aaf8-4d7c-9a56-385c54356eff",
        "url": "https://gsmtasks.com/api/tasks/file_uploads/874965eb-1de6-442a-92f0-2cadbed45716/",
        "file": "https://gsmtasks.com/media/fileupload/874965eb-1de6-442a-92f0-2cadbed45716/attachment.xlsx",
        "size": 8550,
        "created_by": "https://gsmtasks.com/api/tasks/users/12d2821e-01e2-48fb-97bc-eaebca93cbdc/",
        "is_image": false,
        "created_at": "2016-10-20T08:03:14.540726Z",
        "updated_at": "2016-10-20T08:03:14.540759Z"
    }
]
```

`GET https://gsmtasks.com/api/tasks/file_uploads/`

### Attributes

Attribute     | Type    | Description
------------  | ------- | -----------
id            | String  | File Upload unique identifier
url           | String  | Unique URL for the resource
file          | String  | URL of the file for downloading
size          | String  | Size of the file uploaded in bytes
created_by    | String  | URL of the user who created the upload
is_image      | Boolean | Defines if the upload is an image
created_at    | String  | The time when the file upload was created
updated_at    | String  | The time when the order file upload updated

## Create a file upload

Request to create a new file with the parameters provided and the base64 encoded file data.

> Example POST request JSON data:

```json
{
    "file": "https://gsmtasks.com/media/fileupload/d242bb19-d273-4393-84fe-40c2314e558d/Important.jpg",
    "is_image": true
}
```

> The request returns JSON of the created File Upload structured like this:

```json

{
    "id": "d242bb19-d273-4393-84fe-40c2314e558d",
    "url": "https://gsmtasks.com/api/tasks/file_uploads/d242bb19-d273-4393-84fe-40c2314e558d/",
    "file": "https://gsmtasks.com/media/fileupload/d242bb19-d273-4393-84fe-40c2314e558d/Important.jpg",
    "size": 141652,
    "created_by": "https://gsmtasks.com/api/tasks/users/adba000d-9f1b-4469-a2b7-7dfb7977f57b/",
    "is_image": true,
    "created_at": "2016-10-06T11:09:52.856869Z",
    "updated_at": "2016-10-06T11:16:00.563052Z"
    
}
```

`POST https://gsmtasks.com/api/tasks/file_uploads/`

### Request parameters

Parameter     | Type   | Required | Description
------------  | ------ | -------  | -----------
file          | String | Yes      | URL of the file
is_image      | Boolean| -        | Defines if the upload is an image