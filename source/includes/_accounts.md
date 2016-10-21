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
        "address": {
          "raw_address": "Piccadilly Circus, London, United Kingdom",
          "formatted_address": "Piccadilly Circus, London W1D 7ET, UK",
          "location": {
            "type": "Point",
            "coordinates": [
              -0.13457340000002205,
              51.5100974
            ]
          },
          "google_place_id": "ChIJwR8g_9MEdkgR_rI--wzfivA",
          "point_of_interest": "",
          "street": "Piccadilly Circus",
          "house_number": "",
          "apartment_number": "",
          "city": "London",
          "state": "",
          "postal_code": "W1D 7ET",
          "country": "United Kingdom",
          "country_code": "GB"
        },
        "managers": "https://gsmtasks.com/api/tasks/accounts/4368ec5d-9942-4c74-90f7-eea752a6e489/managers/",
        "workers": "https://gsmtasks.com/api/tasks/accounts/4368ec5d-9942-4c74-90f7-eea752a6e489/workers/",
        "task_duration": "00:05:00",
        "dashboard_task_template": "",
        "dashboard_worker_limit": 10,
        "feature_sidebar_task_form": true,
        "feature_task_created_sound": false,
        "feature_change_task_account": false,
        "feature_show_tutorial": false
    }
]
```

`GET https://gsmtasks.com/api/tasks/accounts/`

### Attributes

Attribute                   | Type    | Description
--------------------------- | ------  | -----------
id                          | String  | Account unique identifier
url                         | String  | Unique URL for the resource
name                        | String  | Name of the account for easy reference
slug                        | String  | Machine readable account identifier
timezone                    | String  | [Timezone name](https://en.wikipedia.org/wiki/List_of_tz_database_time_zones) for dates and time
country_code                | String  | ISO 2 [country code](https://en.wikipedia.org/wiki/ISO_3166-1_alpha-2)
address                     | Object  | Address object describing the location of the account
managers                    | String  | URL for easy access to account managers
workers                     | String  | URL for easy access to account workers
task_duration               | String  | 
dashboard_task_template     | String  |  
dashboard_worker_limit      | Integer |
feature_sidebar_task_form   | Boolean |
feature_task_created_sound  | Boolean |
feature_change_task_account | Boolean |
feature_show_tutorial       | Boolean |

## Retrieve a specific Account

`GET https://gsmtasks.com/api/tasks/accounts/4368ec5d-9942-4c74-90f7-eea752a6e489/`

## Create Account

Request to create a new account with the parameters provided

> Example POST request JSON data:

```json
{
    "account": {
        "name": "Fast Couriers",
        "timezone": "Europe/London",
        "country_code": "GB"
    },
    "user": {
        "first_name": "Tom",
        "last_name": "Smith",
        "email": "tom.smith@fast.uk",
        "phone": "+447700900132",
        "password": "password"
    }
}
```

> The request returns JSON of the created Account structured like this:

```json
{
    "account": {
        "id": "4368ec5d-9942-4c74-90f7-eea752a6e489",
        "url": "https://gsmtasks.com/api/tasks/accounts/4368ec5d-9942-4c74-90f7-eea752a6e489/",
        "name": "Fast Couriers",
        "timezone": "Europe/London",
        "country_code": "GB"
    },
    "user": {
        "id": "e04b279e-d8ed-4c12-b4df-698652d4c627",
        "url": "https://gsmtasks.com/api/tasks/users/e04b279e-d8ed-4c12-b4df-698652d4c627/",
        "first_name": "Tom",
        "last_name": "Smith",
        "email": "tom.smith@fast.uk",
        "phone": "++447700900132"
    },
    "token": "5dac4af44f7da18f802cfae8685c00a3de73755b"
}
```

`POST https://gsmtasks.com/api/register/`

### Request parameters

Parameter     | Type   | Required | Description
------------  | ------ | -------  | -----------
name          | String | Yes      | Name of the account for easy reference
timezone      | String | -        | [Timezone name](https://en.wikipedia.org/wiki/List_of_tz_database_time_zones) for dates and time
country_code  | String | No       | ISO 2 [country code](https://en.wikipedia.org/wiki/ISO_3166-1_alpha-2)
user          | object | Yes      | User object 

