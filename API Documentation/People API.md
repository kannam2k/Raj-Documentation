## **API Overview:**

### **Introduction**

Welcome to the swapi, the Star Wars API! This documentation should help you familiarise yourself with the resources available and how to consume them with HTTP requests. If you're after a native helper library then I suggest you scroll down and check out what's available. Read through the getting started section before you dive in. Most of your problems should be solved just by reading through it.

### **Getting started**

Let's make our first API request to the Star Wars API!

Open up a terminal and use curl or httpie to make an API request for a resource. In the example below, we're trying to get the first planet, Tatooine:

> [http://swapi.dev/api/planets/1/](http://swapi.dev/api/planets/1/)

We'll use httpie for our examples as it displays responses nicely and gives us a whole lot more useful information. If you don't want to download httpie, just use the curl command instead.

 **Here is the response we get:**

HTTP/1.0 200 OK

Content-Type: application/json

```
{

    "climate": "Arid",

    "diameter": "10465",

    "gravity": "1 standard",

    "name": "Tatooine",

    "orbital_period": "304",

    "population": "200000",

    "residents": [

        "https://swapi.dev/api/people/1/",

        "https://swapi.dev/api/people/2/",

        ...

    ],

    "rotation_period": "23",

    "surface_water": "1",

    "terrain": "Dessert",

    "url": " https://swapi.dev/api/planets/1/"

}
```

If your response looks slightly different don't panic. This is probably because more data has been added to swapi since we made this documentation.

### **Base URL**

The Base URL is the root URL for all of the API, if you ever make a request to swapi and you get back a 404 NOT FOUND response then check the Base URL first.

### **The Base URL for swapi is:**

> [https://swapi.dev/api/](https://swapi.dev/api/)

The documentation below assumes you are prepending the Base URL to the endpoints in order to make requests.

### **Rate limiting**

Swapi has rate limiting to prevent malicious abuse (as if anyone would abuse Star Wars data!) and to make sure our service can handle a potentially large amount of traffic. Rate limiting is done via IP address and is currently limited to 10,000 API request per day. This is enough to request all the data on the website at least ten times over. There should be no reason for hitting the rate limit. 

### **Authentication**

Swapi is a completely open API. No authentication is required to query and get data. This also means that we've limited what you can do to just GET-ing the data. If you find a mistake in the data, then tweet the author or email him.

### **JSON Schema**

All resources support JSON Schema. Making a request to /api/<resource>/schema will give you the details of that resource. This will allow you to programmatically inspect the attributes of that resource and their types.

### **Searching**

All resources support a search parameter that filters the set of resources returned. This allows you to make queries like:

> [https://swapi.dev/api/people/?search=r2](https://swapi.dev/api/people/?search=r2)

All searches will use case-insensitive partial matches on the set of search fields. To see the set of search fields for each resource, check out the individual resource documentation. For more information on advanced search terms see here.

---

## **API Reference** 

### **People**

A People resource is an individual person or character within the Star Wars universe. This API is used to get all the people resources, get a specific people resource, and view the JSON schema for this resource.

### **Method:** GET

### **Request URL:**

> [https://swapi.dev/api/people](https://swapi.dev/api/people)

### **Request Headers:**

Authorization / Authentication: No Auth

Content Type: application/json

Accept: application/json

### **End Point:**

-   /people/ -- get all the people resources
    
-   /people/:id/ -- get a specific people resource
    
-   /people/schema/ -- view the JSON schema for this resource
    

### **Parameters:**

**Parameter**

**Data Type**

**Description**

Name *

string

The name of this person.

Height *

string

The height of the person in centimeters.

mass *

string

The mass of the person in kilograms.

Hair_color *

string

The hair color of this person. Will be "unknown" if not known or "n/a" if the person does not have hair.

Skin_color *

string

The skin color of this person.

Eye_color *

string

The eye color of this person. Will be "unknown" if not known or "n/a" if the person does not have an eye.

Birth_year *

string

The birth year of the person, using the in-universe standard of BBY or ABY - Before the Battle of Yavin or After the Battle of Yavin. The Battle of Yavin is a battle that occurs at the end of Star Wars episode IV: A New Hope.

gender *

string

The gender of this person. Either "Male", "Female" or "unknown", "n/a" if the person does not have a gender.

Homeworld *

string

The URL of a planet resource, a planet that this person was born on or inhabits.

films *

Array

An array of film resource URLs that this person has been in.

species *

Array

An array of species resource URLs that this person belongs to.

Starships *

Array

An array of starship resource URLs that this person has piloted.

Vehicles *

Array

An array of vehicle resource URLs that this person has piloted.

url *

String

The hypermedia URL of this resource.

Created *

String

The ISO 8601 date format of the time that this resource was created.

Edited *

String

The ISO 8601 date format of the time that this resource was edited.

### **Response Codes:**

Every web code returns a response code to display whether it is successful or had an error.

**Response Code**

**Description**

200 OK

Successful operation

400

Invalid input

404

### **Example Response:**

```
{
"count": 82,

    "next": "https://swapi.dev/api/people/?page=2",

    "previous": null,

    "results": [

        {

            "name": "Luke Skywalker",

            "height": "172",

            "mass": "77",

            "hair_color": "blond",

            "skin_color": "fair",

            "eye_color": "blue",

            "birth_year": "19BBY",

            "gender": "male",

            "homeworld": "https://swapi.dev/api/planets/1/",

            "films": [

                "https://swapi.dev/api/films/1/",

                "https://swapi.dev/api/films/2/",

                "https://swapi.dev/api/films/3/",

                "https://swapi.dev/api/films/6/"

            ],

            "species": [],

            "vehicles": [

                "https://swapi.dev/api/vehicles/14/",

                "https://swapi.dev/api/vehicles/30/"

            ],

            "starships": [

                "https://swapi.dev/api/starships/12/",

                "https://swapi.dev/api/starships/22/"

            ],

            "created": "2014-12-09T13:50:51.644000Z",

            "edited": "2014-12-20T21:17:56.891000Z",

            "url": "https://swapi.dev/api/people/1/"

        },

        {

            "name": "C-3PO",

            "height": "167",

            "mass": "75",

            "hair_color": "n/a",

            "skin_color": "gold",

            "eye_color": "yellow",

            "birth_year": "112BBY",

            "gender": "n/a",

            "homeworld": "https://swapi.dev/api/planets/1/",

            "films": [

                "https://swapi.dev/api/films/1/",

                "https://swapi.dev/api/films/2/",

                "https://swapi.dev/api/films/3/",

                "https://swapi.dev/api/films/4/",

                "https://swapi.dev/api/films/5/",

                "https://swapi.dev/api/films/6/"

            ],

            "species": [

                "https://swapi.dev/api/species/2/"

            ],

            "vehicles": [],

            "starships": [],

            "created": "2014-12-10T15:10:51.357000Z",

            "edited": "2014-12-20T21:17:50.309000Z",

            "url": "https://swapi.dev/api/people/2/"

        },

        {

            "name": "R2-D2",

            "height": "96",

            "mass": "32",

            "hair_color": "n/a",

            "skin_color": "white, blue",

            "eye_color": "red",

            "birth_year": "33BBY",

            "gender": "n/a",

            "homeworld": "https://swapi.dev/api/planets/8/",

            "films": [

                "https://swapi.dev/api/films/1/",

                "https://swapi.dev/api/films/2/",

                "https://swapi.dev/api/films/3/",

                "https://swapi.dev/api/films/4/",

                "https://swapi.dev/api/films/5/",

                "https://swapi.dev/api/films/6/"

            ],

            "species": [

                "https://swapi.dev/api/species/2/"

            ],

            "vehicles": [],

            "starships": [],

            "created": "2014-12-10T15:11:50.376000Z",

            "edited": "2014-12-20T21:17:50.311000Z",

            "url": "https://swapi.dev/api/people/3/"

        },

        {

            "name": "Darth Vader",

            "height": "202",

            "mass": "136",

            "hair_color": "none",

            "skin_color": "white",

            "eye_color": "yellow",

            "birth_year": "41.9BBY",

            "gender": "male",

            "homeworld": "https://swapi.dev/api/planets/1/",

            "films": [

                "https://swapi.dev/api/films/1/",

                "https://swapi.dev/api/films/2/",

                "https://swapi.dev/api/films/3/",

                "https://swapi.dev/api/films/6/"

            ],

            "species": [],

            "vehicles": [],

            "starships": [

                "https://swapi.dev/api/starships/13/"

            ],

            "created": "2014-12-10T15:18:20.704000Z",

            "edited": "2014-12-20T21:17:50.313000Z",

            "url": "https://swapi.dev/api/people/4/"

        },

        {

            "name": "Leia Organa",

            "height": "150",

            "mass": "49",

            "hair_color": "brown",

            "skin_color": "light",

            "eye_color": "brown",

            "birth_year": "19BBY",

            "gender": "female",

            "homeworld": "https://swapi.dev/api/planets/2/",

            "films": [

                "https://swapi.dev/api/films/1/",

                "https://swapi.dev/api/films/2/",

                "https://swapi.dev/api/films/3/",

                "https://swapi.dev/api/films/6/"

            ],

            "species": [],

            "vehicles": [

                "https://swapi.dev/api/vehicles/30/"

            ],

            "starships": [],

            "created": "2014-12-10T15:20:09.791000Z",

            "edited": "2014-12-20T21:17:50.315000Z",

            "url": "https://swapi.dev/api/people/5/"

        },

        {

            "name": "Owen Lars",

            "height": "178",

            "mass": "120",

            "hair_color": "brown, grey",

            "skin_color": "light",

            "eye_color": "blue",

            "birth_year": "52BBY",

            "gender": "male",

            "homeworld": "https://swapi.dev/api/planets/1/",

            "films": [

                "https://swapi.dev/api/films/1/",

                "https://swapi.dev/api/films/5/",

                "https://swapi.dev/api/films/6/"

            ],

            "species": [],

            "vehicles": [],

            "starships": [],

            "created": "2014-12-10T15:52:14.024000Z",

            "edited": "2014-12-20T21:17:50.317000Z",

            "url": "https://swapi.dev/api/people/6/"

        },

        {

            "name": "Beru Whitesun lars",

            "height": "165",

            "mass": "75",

            "hair_color": "brown",

            "skin_color": "light",

            "eye_color": "blue",

            "birth_year": "47BBY",

            "gender": "female",

            "homeworld": "https://swapi.dev/api/planets/1/",

            "films": [

                "https://swapi.dev/api/films/1/",

                "https://swapi.dev/api/films/5/",

                "https://swapi.dev/api/films/6/"

            ],

            "species": [],

            "vehicles": [],

            "starships": [],

            "created": "2014-12-10T15:53:41.121000Z",

            "edited": "2014-12-20T21:17:50.319000Z",

            "url": "https://swapi.dev/api/people/7/"

        },

        {

            "name": "R5-D4",

            "height": "97",

            "mass": "32",

            "hair_color": "n/a",

            "skin_color": "white, red",

            "eye_color": "red",

            "birth_year": "unknown",

            "gender": "n/a",

            "homeworld": "https://swapi.dev/api/planets/1/",

            "films": [

                "https://swapi.dev/api/films/1/"

            ],

            "species": [

                "https://swapi.dev/api/species/2/"

            ],

            "vehicles": [],

            "starships": [],

            "created": "2014-12-10T15:57:50.959000Z",

            "edited": "2014-12-20T21:17:50.321000Z",

            "url": "https://swapi.dev/api/people/8/"

        },

        {

            "name": "Biggs Darklighter",

            "height": "183",

            "mass": "84",

            "hair_color": "black",

            "skin_color": "light",

            "eye_color": "brown",

            "birth_year": "24BBY",

            "gender": "male",

            "homeworld": "https://swapi.dev/api/planets/1/",

            "films": [

                "https://swapi.dev/api/films/1/"

            ],

            "species": [],

            "vehicles": [],

            "starships": [

                "https://swapi.dev/api/starships/12/"

            ],

            "created": "2014-12-10T15:59:50.509000Z",

            "edited": "2014-12-20T21:17:50.323000Z",

            "url": "https://swapi.dev/api/people/9/"

        },

        {

            "name": "Obi-Wan Kenobi",

            "height": "182",

            "mass": "77",

            "hair_color": "auburn, white",

            "skin_color": "fair",

            "eye_color": "blue-gray",

            "birth_year": "57BBY",

            "gender": "male",

            "homeworld": "https://swapi.dev/api/planets/20/",

            "films": [

                "https://swapi.dev/api/films/1/",

                "https://swapi.dev/api/films/2/",

                "https://swapi.dev/api/films/3/",

                "https://swapi.dev/api/films/4/",

                "https://swapi.dev/api/films/5/",

                "https://swapi.dev/api/films/6/"

            ],

            "species": [],

            "vehicles": [

                "https://swapi.dev/api/vehicles/38/"

            ],

            "starships": [

                "https://swapi.dev/api/starships/48/",

                "https://swapi.dev/api/starships/59/",

                "https://swapi.dev/api/starships/64/",

                "https://swapi.dev/api/starships/65/",

                "https://swapi.dev/api/starships/74/"

            ],

            "created": "2014-12-10T16:16:29.192000Z",

            "edited": "2014-12-20T21:17:50.325000Z",

            "url": "https://swapi.dev/api/people/10/"

        }

    ]

}
```
