---
title: GSMtasks documentation - API reference

language_tabs:
  - http
  # - php
  # - python

toc_footers:
  - <a href='https://gsmtasks.com/users/signup/'>Sign Up for a Developer Key</a>

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

search: true
---

# Introduction

The GSMtasks API is a RESTful web service for developers to programmatically interact with GSMtasks data, real-time delivery and task management and route optimization functionality.

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

## Obtaining authorization tokens

To obtain a authorization token the fallowing HTTP request has to be performed.

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

Status code | Status text       | Description
----------- | ----------------- | -----------
200         | OK                | Everything worked as expected.
400         | Bad Request       | Often missing a required parameter.
401         | Unauthorized      | No valid API key provided.
402         | Request Failed    | Parameters were valid but request failed.
404         | Not Found         | The requested item doesn't exist.
429         | Too Many Requests | Too many requests hit the API too quickly.
50*         | Server Errors     | Something went wrong on our end.
