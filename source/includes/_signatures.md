# Signatures

Signatures attach File Upload objects to a task and are meant to separate leagal signatures from documents.

<aside class="notice">
The File Upload object has to be created before creating the Signature object.
</aside>

## List Signatures

Returns a array of signatures that the user has access to.

> The request returns JSON structured like this:

```json
[
  {
    "id": "c6a66d6d-76e0-4c7e-a22c-02eff4d68b59",
    "url": "https://gsmtasks.com/api/tasks/documents/c6a66d6d-76e0-4c7e-a22c-02eff4d68b591/",
    "task": "https://gsmtasks.com/api/tasks/tasks/d09b5fc0-d82f-42ed-9d5f-022d68f36df6/",
    "file": "https://gsmtasks.com/media/fileupload/874965eb-1de6-442a-92f0-2cadbed45716/attachment.xlsx",
    "size": 8550,
    "is_image": false,
    "signer": {
      "name": "Tom ",
      "company": "Smith",
      "phone": "+447700900132",
      "email": "tom.smith@fast.uk",
      "notes": "All good"
    },
    "created_by": "https://gsmtasks.com/api/tasks/users/12d2821e-01e2-48fb-97bc-eaebca93cbdc/",
    "created_at": "2016-10-18T08:34:46.117131Z",
    "updated_at": "2016-10-18T08:34:46.117157Z"
  }
]
```

`GET https://gsmtasks.com/api/tasks/signatures/`

### Attributes

Attribute         | Type    | Description
----------------- | ------- | -----------
id                | String  | Signature unique identifier
url               | String  | Unique URL for the resource
task              | String  | URL of the task resource
file              | String  | URL of the file for downloading
size              | Number  | Size of the file in bytes
signer            | Object  | Signer object of the signature
created_by        | String  | URL of the user who created the signature
created_at       | String  | The time when the signature was created
updated_at        | String  | The time when the signature was updated


## Create Signature

Request to create a new document with the parameters provided

> Example POST request JSON data:

```json
{
  "task": "https://gsmtasks.com/api/tasks/tasks/d09b5fc0-d82f-42ed-9d5f-022d68f36df6/",
  "file_upload": "https://gsmtasks.com/api/tasks/file_uploads/874965eb-1de6-442a-92f0-2cadbed45716/",
  "signer": {
    "name": "Tom ",
    "company": "Smith",
    "phone": "+447700900132",
    "email": "tom.smith@fast.uk",
    "notes": "Call 5 minutes before"
  }
}
```

> The request returns JSON of the created Signature structured like this:

```json
{
  "id": "c6a66d6d-76e0-4c7e-a22c-02eff4d68b59",
  "url": "https://gsmtasks.com/api/tasks/documents/c6a66d6d-76e0-4c7e-a22c-02eff4d68b591/",
  "task": "https://gsmtasks.com/api/tasks/tasks/d09b5fc0-d82f-42ed-9d5f-022d68f36df6/",
  "file": "https://gsmtasks.com/media/fileupload/874965eb-1de6-442a-92f0-2cadbed45716/attachment.xlsx",
  "size": 8550,
  "is_image": false,
  "signer": {
    "name": "Tom ",
    "company": "Smith",
    "phone": "+447700900132",
    "email": "tom.smith@fast.uk",
    "notes": "All good"
  },
  "created_by": "https://gsmtasks.com/api/tasks/users/12d2821e-01e2-48fb-97bc-eaebca93cbdc/",
  "created_at": "2016-10-18T08:34:46.117131Z",
  "updated_at": "2016-10-18T08:34:46.117157Z"
}
```

`POST https://gsmtasks.com/api/tasks/signatures/`

### Request parameters

Attribute         | Required | Type    | Description
----------------- | -------- | ------- | -----------
task              | Yes      | String  | URL of the task resource
file_upload       | Yes      | String  | URL of the file upload object
signer            | Yes      | Oject   | Signer object
