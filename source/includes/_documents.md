# Documents

Documents attach File Upload objects to a task.

<aside class="notice">
The File Upload object has to be created before creating the Document object.
</aside>

## List Document

Returns a array of documents that the user has access to.

> The request returns JSON structured like this:

```json
[
  {
    "id": "c6a66d6d-76e0-4c7e-a22c-02eff4d68b59",
    "url": "https://gsmtasks.com/api/tasks/documents/c6a66d6d-76e0-4c7e-a22c-02eff4d68b591/",
    "task": "https://gsmtasks.com/api/tasks/tasks/d09b5fc0-d82f-42ed-9d5f-022d68f36df6/",
    "order": null,
    "file": "https://gsmtasks.com/media/fileupload/874965eb-1de6-442a-92f0-2cadbed45716/attachment.xlsx",
    "size": 8550,
    "description": "Attached Excel spreadsheet",
    "created_by": "https://gsmtasks.com/api/tasks/users/12d2821e-01e2-48fb-97bc-eaebca93cbdc/",
    "visible_to_worker": true,
    "visible_to_client": true
  }
]
```

`GET https://gsmtasks.com/api/tasks/documents/`

### Attributes

Attribute         | Type    | Description
----------------- | ------- | -----------
id                | String  | Document unique identifier
url               | String  | Unique URL for the resource
task              | String  | URL of the task resource
order             | String  | URL of the order resource
file              | String  | URL of the file for downloading
size              | Number  | Size of the file uploaded in bytes
description       | String  | Description of the file attached
created_by        | String  | URL of the user who created the upload
visible_to_worker | Boolean | Defines if the document is visible for worker
visible_to_client | Boolean | Defines if the document is visible to orderer / client

## Create Document

Request to create a new document with the parameters provided

> Example POST request JSON data:

```json
{
  "task": "https://gsmtasks.com/api/tasks/tasks/d09b5fc0-d82f-42ed-9d5f-022d68f36df6/",
  "order": "https://gsmtasks.com/api/tasks/orders/4336f911-32ec-4fb4-b17a-e58aef3943e6/",
  "file_upload": "https://gsmtasks.com/api/tasks/file_uploads/874965eb-1de6-442a-92f0-2cadbed45716/",
  "description": "Attached Excel spreadsheet",
  "visible_to_worker": true,
  "visible_to_client": true
}
```

> The request returns JSON of the created Document structured like this:

```json
{
  "id": "c6a66d6d-76e0-4c7e-a22c-02eff4d68b59",
  "url": "https://gsmtasks.com/api/tasks/documents/c6a66d6d-76e0-4c7e-a22c-02eff4d68b591/",
  "task": "https://gsmtasks.com/api/tasks/tasks/d09b5fc0-d82f-42ed-9d5f-022d68f36df6/",
  "order": null,
  "file": "https://gsmtasks.com/media/fileupload/874965eb-1de6-442a-92f0-2cadbed45716/attachment.xlsx",
  "size": 8550,
  "description": "Attached Excel spreadsheet",
  "created_by": "https://gsmtasks.com/api/tasks/users/12d2821e-01e2-48fb-97bc-eaebca93cbdc/",
  "visible_to_worker": true,
  "visible_to_client": true
}
```

`POST https://gsmtasks.com/api/tasks/documents/`

### Request parameters

Attribute         | Required | Type    | Description
----------------- | -------- | ------- | -----------
task              | Yes      | String  | URL of the task resource
order             | Yes      | String  | URL of the order resource
file_upload       | Yes      | String  | URL of the file upload object
description       | No       | String  | Description of the file attached
visible_to_worker | Yes      | Boolean | Defines if the document is visible for worker
visible_to_client | Yes      | Boolean | Defines if the document is visible to orderer / client
