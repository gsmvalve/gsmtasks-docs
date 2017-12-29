---
title: GSMtasks documentation - API reference

<<<<<<< HEAD
language_tabs:
  - http
  # - php
  # - python

toc_footers:
  - <a href='https://gsmtasks.com/users/signup/'>Sign Up for a Developer Key</a>
=======
language_tabs: # must be one of https://git.io/vQNgJ
  - shell
  - ruby
  - python
  - javascript

toc_footers:
  - <a href='#'>Sign Up for a Developer Key</a>
  - <a href='https://github.com/lord/slate'>Documentation Powered by Slate</a>
>>>>>>> upstream/master

includes:
  - accounts
  - accountroles
  - users
  - orders
  - tasks
  - taskevents
  - contactaddresses
  - trackers
  - routeoptimizations
  - fileuploads
  - documents
  - signatures
  - clients
  - task_metadatas
  - task_forms
  - task_event_tracks
  - task_address_features
  - metafields
  - notifications
  - notification_templates
  - time_locations
  
search: true
---

# Introduction

<<<<<<< HEAD
The GSMtasks API is a RESTful web service for developers to programmatically interact with GSMtasks data, real-time delivery and task management and route optimization functionality.
=======
Welcome to the Kittn API! You can use our API to access Kittn API endpoints, which can get information on various cats, kittens, and breeds in our database.

We have language bindings in Shell, Ruby, and Python! You can view code examples in the dark area to the right, and you can switch the programming language of the examples with the tabs in the top right.

This example API documentation page was created with [Slate](https://github.com/lord/slate). Feel free to edit it and use it as a base for your own API's documentation.

# Authentication

> To authorize, use this code:

```ruby
require 'kittn'
>>>>>>> upstream/master

The GSMtasks API is organized around REST. Every bit of data exchanged between clients and the API is JSON over HTTPS. All API requests must be made over HTTPS. Calls made over plain HTTP will fail. You must authenticate for all requests.

The base URL for the GSMTasks API is https://gsmtasks.com/api/tasks/.

If you have questions about using the API, or have come across a bug you'd like to report, write us an email at <info@gsmtasks.com>.

## Authentication

For clients to authenticate, the token key should be included in the Authorization HTTP header.

The key should be prefixed by the string literal "Token", with whitespace separating the two strings.

`Authorization: Token 9944b09199c62bcf9418ad846dd0e4bbdfc6ee4b`

<aside class="notice">
You must replace <code>9944b09199c62bcf9418ad846dd0e4bbdfc6ee4b</code> with your personal API key.
</aside>

Unauthenticated responses that are denied permission will result in an HTTP 401 Unauthorized response with an appropriate WWW-Authenticate header.

`WWW-Authenticate: Token`

## Obtaining authentication tokens

To obtain a authentication token the fallowing HTTP request has to be performed.

> The request returns JSON structured like this:

```json
{
  "account": "4368ec5d-9942-4c74-90f7-eea752a6e489",
  "token": "7e9917ffg57b043b9527711395c013761b2113c7",
  "accounts": [
    "4368ec5d-9942-4c74-90f7-eea752a6e489",
    "5941c788-f162-4ad0-a43a-4af82bcb30b6"
  ],
  "user": "https://gsmtasks.com/api/tasks/users/85410f5f-ec82-4148-ba78-5be5a79f0fb1/"
}
```

### HTTP Request

`POST https://gsmtasks.com/api/authenticate/`

### Query Parameters

Parameter | Type   | Required | Description
--------- | ------ | -------  | -----------
username  | String | yes      | The email used during signup
password  | String | yes      | The password set for that username

<aside class="success">
The tokens are valid forever, unless refreshed by the user himself.
</aside>

## Errors

GSMtasks uses conventional HTTP response codes to indicate success or failure of an API request. In general, codes in the 2xx range indicate success, codes in the 4xx range indicate an error that resulted from the provided information (e.g. a required parameter was missing, a charge failed, etc.), and codes in the 5xx range indicate an error with GSMtasks's servers.

<<<<<<< HEAD
Status code | Status text       | Description
----------- | ----------------- | -----------
200         | OK                | Everything worked as expected.
400         | Bad Request       | Often missing a required parameter.
401         | Unauthorized      | No valid API key provided.
402         | Request Failed    | Parameters were valid but request failed.
404         | Not Found         | The requested item doesn't exist.
429         | Too Many Requests | Too many requests hit the API too quickly.
50*         | Server Errors     | Something went wrong on our end.
=======
## Delete a Specific Kitten

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.kittens.delete(2)
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
api.kittens.delete(2)
```

```shell
curl "http://example.com/api/kittens/2"
  -X DELETE
  -H "Authorization: meowmeowmeow"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
let max = api.kittens.delete(2);
```

> The above command returns JSON structured like this:

```json
{
  "id": 2,
  "deleted" : ":("
}
```

This endpoint deletes a specific kitten.

### HTTP Request

`DELETE http://example.com/kittens/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the kitten to delete

>>>>>>> upstream/master
