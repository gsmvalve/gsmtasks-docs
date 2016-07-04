# Accounts

This is an object representing your GSMtasks account and it's settings. On signup an account is created for the user. It's also possible to have access to other accounts through Role objects.

<aside class="notice">
Account objects also expose workers and managers endpoints for easy access.
</aside>

## List Accounts

Returns a array of accounts that the user has access to.

> The request returns JSON structured like this:

```json
[
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
]
```

`GET https://gsmtasks.com/api/tasks/accounts/`

### Attributes

Attribute     | Type   | Required | Description
------------  | ------ | -------  | -----------
id            | String | -        | Account unique identifier
url           | String | -        | Unique URL for the resource
name          | String | Yes      | Name of the account for easy reference
slug          | String | -        | Human readable account identifier
timezone      | String | -        | [Timezone name](https://en.wikipedia.org/wiki/List_of_tz_database_time_zones) for dates and time
country_code  | String | No       | ISO 2 [country code](https://en.wikipedia.org/wiki/ISO_3166-1_alpha-2)
managers      | String | -        | URL for easy access to account managers
workers       | String | -        | URL for easy access to account workers

## Retrieve a specific Account

`GET https://gsmtasks.com/api/tasks/task/4368ec5d-9942-4c74-90f7-eea752a6e489/`

## Create Account

Request to create a new account with the parameters provided

> Example POST request JSON data:

```json
{
  "name": "Fast Couriers",
  "timezone": "Europe/London",
  "country_code": "GB"
}
```

> The request returns JSON of the created account structured like this:

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
