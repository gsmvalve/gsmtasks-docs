# File uploads

To attach a file to a Task or Order. The file has to be uploaded via this endpoint.

<aside class="notice">
Account objects also expose workers and managers endpoints for easy access.
</aside>

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
        "is_image": false
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
is_image      | Boolean | If the upload is an image

## Create a file upload

Request to create a new file with the parameters provided and the base64 encoded file data.

> Example POST request JSON data:

```json
{
  "name": "Fast Couriers",
  "timezone": "Europe/London",
  "country_code": "GB"
}
```

> The request returns JSON of the created File Upload structured like this:

```json
{
  "id": "4368ec5d-9942-4c74-90f7-eea752a6e489",
  "url": "https://gsmtasks.com/api/tasks/accounts/4368ec5d-9942-4c74-90f7-eea752a6e489/",
  "name": "Fast Couriers",
  "slug": "fast-couriers",
  "timezone": "Europe/London",
  "country_code": "GB",
  "managers": "https://gsmtasks.com/api/tasks/accounts/4368ec5d-9942-4c74-90f7-eea752a6e489/managers/",
  "workers": "https://gsmtasks.com/api/tasks/accounts/4368ec5d-9942-4c74-90f7-eea752a6e489/workers/"
}
```

`POST https://gsmtasks.com/api/tasks/accounts/`

### Request parameters

Parameter     | Type   | Required | Description
------------  | ------ | -------  | -----------
name          | String | Yes      | Name of the account for easy reference
timezone      | String | -        | [Timezone name](https://en.wikipedia.org/wiki/List_of_tz_database_time_zones) for dates and time
country_code  | String | No       | ISO 2 [country code](https://en.wikipedia.org/wiki/ISO_3166-1_alpha-2)
