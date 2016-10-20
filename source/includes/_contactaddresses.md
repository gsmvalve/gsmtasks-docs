# Contact Addresses

The Contact Address objects as the name describes are a combination of a Contact object and a Address object. Together they are unique. Once created they can be re-used for future tasks and autocompletion.


## List Contact Addresses

Returns a array of Contact Addresses that the user has access to.

> The request returns JSON structured like this:

```json
[
  {
    "id": "a36ff250-df3d-4515-af4a-14c48558b297",
    "url": "https://gsmtasks.com/api/tasks/contact_addresses/a36ff250-df3d-4515-af4a-14c48558b297/",
    "account": "https://gsmtasks.com/api/tasks/accounts/4f946a84-fb06-43ac-b98d-d2b38bbe307a/",
    "client": "https://gsmtasks.com/api/tasks/clients/b233dd8f-aeee-4a5f-8c0e-a95657186cf9/",
    "contact": {
      "name": "Tom ",
      "company": "Smith",
      "phone": "+447700900132",
      "email": "tom.smith@fast.uk",
      "notes": "Call 5 minutes before"
    },
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
    "created_at": "2016-10-06T11:09:52.856869Z",
    "updated_at": "2016-10-06T11:16:00.563052Z"
  }
]
```

`GET https://gsmtasks.com/api/tasks/contact_addresses/`

### Attributes

Attribute     | Type   | Description
------------  | ------ | -----------
id            | String | Contact Address unique identifier
url           | String | Unique URL for the resource
account       | String | URL of the account resource
client        | String | URL of the client resource
contact       | Object | Contact object
address       | Object | Address object
created_at   | String | The time when the contact address was created
updated_at    | String | The time when the contact address was updated

## Retrieve a specific Contact Address

`GET https://gsmtasks.com/api/tasks/contact_addresses/a36ff250-df3d-4515-af4a-14c48558b297/`

## Create Contact Address

Request to create a new Contact Address with the parameters provided

> Example POST request JSON data:

```json
{
  "account": "https://gsmtasks.com/api/tasks/accounts/4f946a84-fb06-43ac-b98d-d2b38bbe307a/",
  "client": "https://gsmtasks.com/api/tasks/clients/b233dd8f-aeee-4a5f-8c0e-a95657186cf9/",
  "contact": {
    "name": "Tom ",
    "company": "Smith",
    "phone": "+447700900132",
    "email": "tom.smith@fast.uk",
    "notes": "Call 5 minutes before"
  },
  "address": {
    "raw_address": "Piccadilly Circus, London, United Kingdom"
  }
}
```

> The request returns JSON of the created Contact Address structured like this:

```json
{
  "id": "a36ff250-df3d-4515-af4a-14c48558b297",
  "url": "https://gsmtasks.com/api/tasks/contact_addresses/a36ff250-df3d-4515-af4a-14c48558b297/",
  "account": "https://gsmtasks.com/api/tasks/accounts/4f946a84-fb06-43ac-b98d-d2b38bbe307a/",
  "client": "https://gsmtasks.com/api/tasks/clients/b233dd8f-aeee-4a5f-8c0e-a95657186cf9/",
  "contact": {
    "name": "Tom ",
    "company": "Smith",
    "phone": "+447700900132",
    "email": "tom.smith@fast.uk",
    "notes": "Call 5 minutes before"
  },
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
  "created_at": "2016-10-06T11:09:52.856869Z",
  "updated_at": "2016-10-06T11:16:00.563052Z"
}
```

`POST https://gsmtasks.com/api/tasks/contact_addresses/`

### Request parameters

Parameter     | Type   | Required | Description
------------  | ------ | -------  | -----------
account       | String | Yes      | URL of the account resource
client        | String | No       | URL of the client resource
contact       | Object | Yes      | Contact object
address       | Object | Yes      | Address object
