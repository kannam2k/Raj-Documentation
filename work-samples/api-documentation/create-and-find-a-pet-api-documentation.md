---
icon: paw
---

# Create and Find a Pet   API Documentation

## Introduction

This API is used to add a new pet to the store.

## POST

**Method:** `POST`

**Base URL:**

`https://petstore3.swagger.io/api/v3/pet`

**Request Headers:**

* Authorization / Authentication: No Auth
* Content Type: application/json
* Accept: application/json

**End Point:**

`/pet`

**Parameters:**

| **Attribute** | **Data Type**   | **Notes**                                                | **Description**                                                                                 |
| ------------- | --------------- | -------------------------------------------------------- | ----------------------------------------------------------------------------------------------- |
| Id            | integer         | Any integer value (int64-signed 64 bits)                 | **Required**. This is a unique ID assigned to every pet that is added in the store.             |
| Name          | String          | An associative array of name/value pairs                 | **Required**. This is the name of the Pet.                                                      |
| Category      | Category Object | List of id and name objects                              | **Required**. Defines category to which the new Pet should belong to.                           |
| Id            | Integer         | Any integer value (int64-signed 64 bits)                 | **Required**. This is a unique ID assigned to every categorized pet that is added in the store. |
| name          | string          | -                                                        | **Required**. Name of the category.                                                             |
| photoUrls     | string          | Array of URLs                                            | Link of the image                                                                               |
| Tags          | Tag Object      | Array of Tag objects                                     | List of tag objects to specify each pet                                                         |
| Id            | integer         | Any integer value (int64-signed 64 bits)                 | This is a unique ID assigned to each tag                                                        |
| name          | string          | -                                                        | Tag name of the Pet                                                                             |
| Status        | string          | <ul><li>Available</li><li>Pending</li><li>Sold</li></ul> | **Required**. Pet status in the store.                                                          |

**Response Codes:**

Every web code returns a response code to display whether it is successful or had an error.

| **Response Code** | **Description**      |
| ----------------- | -------------------- |
| 200 OK            | Successful operation |
| 405               | Invalid input        |

**Sample Request:**

```json
{
  "id": 1459,
  "name": "Johnny",
  "category": {
    "id": 1,
    "name": "German Shepherd"
  },
  "photoUrls": [
    "string"
  ],
  "tags": [
    {
      "id": 0,
      "name": "string"
    }
  ],
  "status": "available"
}
```

**Response Body:**

```json
{
  "id": 1459,
  "category": {
    "id": 1,
    "name": "Dogs"
  },
  "name": "johnny",
  "photoUrls": [
    "https://upload.wikimedia.org/wikipedia/commons/d/d0/German_Shepherd_-_DSC_0346_%2810096362833%29.jpg"
  ],
  "tags": [
    {
      "id": 1,
      "name": "German Shephard"
    }
  ],
  "status": "available"
}
```

**Response headers:**

* Content-length: 242
* Content-type: application/json

## GET - Find a pet with findbystatus

**Method:** `GET`

This method is used to find pets by status.

**Base URL:** [https://petstore3.swagger.io/api/v3/pet/findByStatus?status=available](https://petstore3.swagger.io/api/v3/pet/findByStatus?status=available)

**Request Headers:**

* Authorization / Authentication: No Auth
* Content Type: application/json
* Accept: application/json

**Query Parameter:**

Status = Available

**End Point:**

`GET/pet/findByStatus`

**Parameters:**

| **Attribute** | **Data Type**   | **Notes**                                                | **Description**                                                                                 |
| ------------- | --------------- | -------------------------------------------------------- | ----------------------------------------------------------------------------------------------- |
| Id            | integer         | Any integer value (int64-signed 64 bits)                 | **Required**. This is a unique ID assigned to every pet that is added in the store.             |
| Name          | String          | An associative array of name/value pairs                 | **Required**. This is the name of the Pet.                                                      |
| Category      | Category Object | List of id and name objects                              | **Required**. Defines category to which the new Pet should belong to.                           |
| Id            | Integer         | Any integer value (int64-signed 64 bits)                 | **Required**. This is a unique ID assigned to every categorized pet that is added in the store. |
| name          | string          | -                                                        | **Required**. Name of the category.                                                             |
| photoUrls     | string          | Array of URLs                                            | Link of the image                                                                               |
| Tags          | Tag Object      | Array of Tag objects                                     | List of tag objects to specify each pet                                                         |
| Id            | integer         | Any integer value (int64-signed 64 bits)                 | This is a unique ID assigned to each tag                                                        |
| name          | string          | -                                                        | Tag name of the Pet                                                                             |
| Status        | string          | <ul><li>Available</li><li>Pending</li><li>Sold</li></ul> | **Required**. Pet status in the store.                                                          |

**Response codes:**

Every web code returns a response code to display whether it is successful or had an error.

| **Response Code** | **Description**      |
| ----------------- | -------------------- |
| 200 OK            | Successful operation |
| 400               | Invalid status value |

**Response headers:**

* Content-length: 2973
* Content-type: application/json

**Response Body Example:**

```json
[
  {
    "id": 4,
    "category": {
      "id": 1,
      "name": "Dogs"
    },
    "name": "Dog 1",
    "photoUrls": [
      "url1",
      "url2"
    ],
    "tags": [
      {
        "id": 1,
        "name": "tag1"
      },
      {
        "id": 2,
        "name": "tag2"
      }
    ],
    "status": "available"
  },
  {
    "id": 1010,
    "category": {
      "id": 2,
      "name": "Cats"
    },
    "name": "Goutam",
    "photoUrls": [
      "string"
    ],
    "tags": [
      {
        "id": 1010,
        "name": "Goutham"
      }
    ],
    "status": "available"
  },
  {
    "id": 4545,
    "category": {
      "id": 2,
      "name": "Fish"
    },
    "name": "motu",
    "photoUrls": [
      "string"
    ],
    "tags": [
      {
        "id": 0,
        "name": "string"
      }
    ],
    "status": "available"
  },
  {
    "id": 374,
    "category": {
      "id": 1,
      "name": "CatUpdated"
    },
    "name": "Pet374Updated",
    "photoUrls": [
      "www.url_updated.com"
    ],
    "tags": [
      {
        "id": 1,
        "name": "tag1Updated"
      }
    ],
    "status": "available"
  },
  {
    "id": 376,
    "category": {
      "id": 1,
      "name": "Cat"
    },
    "name": "Pet376",
    "photoUrls": [
      "www.url.com"
    ],
    "tags": [
      {
        "id": 1,
        "name": "tag1"
      }
    ],
    "status": "available"
  },
  {
    "id": 375,
    "category": {
      "id": 1,
      "name": "CatUpdated"
    },
    "name": "Pet375Updated",
    "photoUrls": [
      "www.url_updated.com"
    ],
    "tags": [
      {
        "id": 1,
        "name": "tag1Updated"
      }
    ],
    "status": "available"
  },
  {
    "id": 377,
    "category": {
      "id": 1,
      "name": "Cat"
    },
    "name": "Pet377",
    "photoUrls": [
      "www.url.com"
    ],
    "tags": [
      {
        "id": 1,
        "name": "tag1"
      }
    ],
    "status": "available"
  },
  {
    "id": 9,
    "category": {
      "id": 1,
      "name": "Dogs"
    },
    "name": "barbos",
    "photoUrls": [
      "string"
    ],
    "tags": [
      {
        "id": 0,
        "name": "string"
      }
    ],
    "status": "available"
  },
  {
    "id": 4444,
    "category": {
      "id": 1,
      "name": "Dogs"
    },
    "name": "doggie",
    "photoUrls": [
      "string"
    ],
    "tags": [
      {
        "id": 0,
        "name": "string"
      }
    ],
    "status": "available"
  },
  {
    "id": 8,
    "category": {
      "id": 11,
      "name": "\""
    },
    "name": "****",
    "photoUrls": [
      "************************"
    ],
    "tags": [
      {
        "id": 1,
        "name": "*"
      }
    ],
    "status": "available"
  },
  {
    "id": 42,
    "category": {
      "id": 1,
      "name": "Dogs"
    },
    "name": "dogge",
    "photoUrls": [
      "string"
    ],
    "tags": [
      {
        "id": 42,
        "name": "dogge"
      }
    ],
    "status": "available"
  },
  {
    "id": 1994,
    "category": {
      "id": 1,
      "name": "Dogs"
    },
    "name": "Lea",
    "photoUrls": [],
    "tags": [
      {
        "id": 0,
        "name": "string"
      }
    ],
    "status": "available"
  },
  {
    "id": 2324,
    "category": {
      "id": 1,
      "name": "Dogs"
    },
    "name": "test_shres",
    "photoUrls": [
      "string"
    ],
    "tags": [
      {
        "id": 0,
        "name": "string"
      }
    ],
    "status": "available"
  },
  {
    "id": 1242342342340,
    "category": {
      "id": 1,
      "name": "Dogs"
    },
    "name": "aeex",
    "photoUrls": [],
    "tags": [
      {
        "id": 0,
        "name": "string"
      }
    ],
    "status": "available"
  },
  {
    "id": 1290,
    "category": {
      "id": 7,
      "name": "Elephant"
    },
    "name": "tom",
    "photoUrls": [
      "string"
    ],
    "tags": [
      {
        "id": 1,
        "name": "tag3"
      }
    ],
    "status": "available"
  },
  {
    "id": -2,
    "category": {
      "id": 1,
      "name": "Dogs"
    },
    "name": "doggie",
    "photoUrls": [
      "string"
    ],
    "tags": [
      {
        "id": 0,
        "name": "string"
      }
    ],
    "status": "available"
  },
  {
    "id": 521,
    "category": {
      "id": 1,
      "name": "Smarty"
    },
    "name": "Cat",
    "photoUrls": [
      "string"
    ],
    "tags": [
      {
        "id": 0,
        "name": "string"
      }
    ],
    "status": "available"
  },
  {
    "id": 10,
    "category": {
      "id": 1,
      "name": "Dogs"
    },
    "name": "doggie",
    "photoUrls": [
      "string"
    ],
    "tags": [
      {
        "id": 0,
        "name": "string"
      }
    ],
    "status": "available"
  },
  {
    "id": 20,
    "category": {
      "id": 1,
      "name": "Dogs"
    },
    "name": "doggie",
    "photoUrls": [
      "string"
    ],
    "tags": [
      {
        "id": 0,
        "name": "Tommy"
      }
    ],
    "status": "available"
  },
  {
    "id": 1459,
    "category": {
      "id": 1,
      "name": "Dogs"
    },
    "name": "johnny",
    "photoUrls": [
      "https://upload.wikimedia.org/wikipedia/commons/d/d0/German_Shepherd_-_DSC_0346_%2810096362833%29.jpg"
    ],
    "tags": [
      {
        "id": 1,
        "name": "German Shephard"
      }
    ],
    "status": "available"
  }
]
```
