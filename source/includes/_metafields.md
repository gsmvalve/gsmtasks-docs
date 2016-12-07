# Metafields

## List Metafields

Returns a array of metafields that the user has access to.

> The request returns JSON structured like this:

```json
[
    {
        "id": "b0f05cbb-4022-4cf8-b471-373b1bfbd1b5",
        "url": "https://gsmtasks.com/api/tasks/metafields/b0f05cbb-4022-4cf8-b471-373b1bfbd1b5/",
        "account": "https://gsmtasks.com/api/tasks/accounts/a6f60fdf-d87b-4c5d-b5ec-67a90cd16236/",
        "namespace": "account",
        "key": "metafield1",
        "field_name": "account:metafield1",
        "value_type": "string",
        "label": "App",
        "choices": null,
        "is_editable": true,
        "show_in_detail_view": true,
        "show_in_list_view": true,
        "show_in_mobile_app": true,
        "created_at": "2016-02-25T13:05:39.140375Z",
        "updated_at": "2016-10-05T14:17:43.191265Z"
    }
]
```

`GET https://gsmtasks.com/api/tasks/metafields/`

### Attributes

Attribute           | Type   | Description
------------------- | ------ | -----------
id                  | String | Client unique identifier
url                 | String | Unique URL for the resource
account             | String | URL of the account resource
namespace           | String | Namespace of this metafield which defines the scope of the attribute, e.g. 'account'
key                 | String | Key of this metafield, which names the attribute key in the metafields dict
field_name          | String | 
value_type          | String | 
label               | String | 
choices             | Array  | 
is_editable         | Boolean| 
show_in_detail_view | Boolean| 
show_in_list_view   | Boolean| 
show_in_mobile_app  | Boolean| 
created_at          | String | The time when the metafield was created
updated_at          | String | The time when the metafield was updated

## Retrieve a specific Metafield

`GET https://gsmtasks.com/api/tasks/metafields/b0f05cbb-4022-4cf8-b471-373b1bfbd1b5/`

## Create Metafield

Request to create a new Metafield with the parameters provided.

> Example POST request JSON data:

```json
{
    "account": "https://gsmtasks.com/api/tasks/accounts/a6f60fdf-d87b-4c5d-b5ec-67a90cd16236/",
    "namespace": "account",
    "key": "metafield1",
    "value_type": "string",
    "label": "App",
    "choices": ["choice 1", "choice 2"],
    "is_editable": true,
    "show_in_detail_view": true,
    "show_in_list_view": true,
    "show_in_mobile_app": true
}
```

> The request returns JSON of the created Order structured like this:

```json
    {
        "id": "b0f05cbb-4022-4cf8-b471-373b1bfbd1b5",
        "url": "https://gsmtasks.com/api/tasks/metafields/b0f05cbb-4022-4cf8-b471-373b1bfbd1b5/",
        "account": "https://gsmtasks.com/api/tasks/accounts/a6f60fdf-d87b-4c5d-b5ec-67a90cd16236/",
        "namespace": "account",
        "key": "metafield1",
        "field_name": "account:metafield1",
        "value_type": "string",
        "label": "App",
        "choices": null,
        "is_editable": true,
        "show_in_detail_view": true,
        "show_in_list_view": true,
        "show_in_mobile_app": true,
        "created_at": "2016-02-25T13:05:39.140375Z",
        "updated_at": "2016-10-05T14:17:43.191265Z"
    }
```

`POST https://gsmtasks.com/api/tasks/metafields/`

### Request parameters

Parameter             | Type   | Required | Description
--------------------- | ------ | -------  | -----------
account               | String | Yes      | URL of the account resource
namespace             | String | Yes      | Namespace of this metafield which defines the scope of the attribute, e.g. 'account'
key                   | String | Yes      | Key of this metafield, which names the attribute key in the metafields dict
value_type            | String | Yes      |
label                 | String | No       |
choices               | Array  | No       |
is_editable           | Boolean| No       |
show_in_detail_view   | Boolean| No       |
show_in_list_view     | Boolean| No       |
show_in_mobile_app    | Boolean| No       |

## Update Metafield

Request to update a Metafield. We will change the namespace and key as an example.

> Example PUT request JSON data:

```json
{
    "account": "https://gsmtasks.com/api/tasks/accounts/a6f60fdf-d87b-4c5d-b5ec-67a90cd16236/",
    "namespace": "metafield",
    "key": "updated"
}
```

> The request returns JSON of the updated Order structured like this:

```json
{
    "id": "b0f05cbb-4022-4cf8-b471-373b1bfbd1b5",
    "url": "https://gsmtasks.com/api/tasks/metafields/b0f05cbb-4022-4cf8-b471-373b1bfbd1b5/",
    "account": "https://gsmtasks.com/api/tasks/accounts/a6f60fdf-d87b-4c5d-b5ec-67a90cd16236/",
    "namespace": "metafield",
    "key": "updated",
    "field_name": "metafield:updated",
    "value_type": "string",
    "label": "App",
    "choices": null,
    "is_editable": true,
    "show_in_detail_view": true,
    "show_in_list_view": true,
    "show_in_mobile_app": true,
    "created_at": "2016-02-25T13:05:39.140375Z",
    "updated_at": "2016-10-05T14:17:43.191265Z"
}
```

`PUT https://gsmtasks.com/api/tasks/clients/74c08598-08b8-46bc-9da7-8b85f7168f20/`

### Request parameters

Parameter             | Type   | Required | Description
--------------------- | ------ | -------  | -----------
account               | String | Yes      | URL of the account resource
namespace             | String | Yes      | Namespace of this metafield which defines the scope of the attribute, e.g. 'account'
key                   | String | Yes      | Key of this metafield, which names the attribute key in the metafields dict
value_type            | String | Yes      |
label                 | String | No       |
choices               | Array  | No       |
is_editable           | Boolean| No       |
show_in_detail_view   | Boolean| No       |
show_in_list_view     | Boolean| No       |
show_in_mobile_app    | Boolean| No       |
