---

title: /favorites
layout: default
parent: Endpoints
---
# /favorites

Get your favorites. Authentication is required.
## Request
**HTTP Methods**: GET, POST
### Fields:
* `count` (int) [optional]: How many updates you get in the response (until 40, default is 10)
* `page` (int) [optional]: This field specifies the page number of the results you want to retrieve. (minimum 1)
* `full` (boolean) [optional]: When "true" is set, it should return more information about the updates, for example when the user is replying to a status a `reply` field should be set, and other fields, mentioned below.

**Example:** `/v1/favorites.xml?full=true`

## Responses

### HTTP Status
- `200` - Successfully 
- `400` - Validation error, or other errors
- `401` - Invalid login details

### Body

In a successful response, it should return the following fields:

#### Fields:
* `user` (User object)
* `text` (string)
* `created_at` (timestamp): When the status was created.
* `source` (string): App used for creating the status.
#### The following fields should only appear when full is set to true:
* `favorited` (bool): If you favorited this update or not.
* `reply` (object) [optional] with `reply.user` (User object) [optional] and `reply.id`

A successful response (with full field set to true) should look like this:

##### XML:
```xml
<statuses>
    <status>
        <user>
            <name>Owler</name>
            <screen_name>owler</screen_name>
            <id>65c1421a1897e7840ad8d315</id>
            <protected>false</protected>
            <profile_image_url>https://picsum.photos/48/48</profile_image_url>
        </user>
        <text>what are you doing?</text>
        <id>20</id>
        <created_at>Wed Nov 08 20:48:50 GMT 2023</created_at>
        <source>web</source>
        <favorited>true</favorited>
    </status>
    <status>
        <user>
            <name>Owler</name>
            <screen_name>owler</screen_name>
            <id>65c1421a1897e7840ad8d315</id>
            <protected>false</protected>
            <profile_image_url>https://picsum.photos/48/48</profile_image_url>
        </user>
        <text>testing the api!</text>
        <id>10</id>
        <created_at>Wed Nov 08 20:47:50 GMT 2023</created_at>
        <source>api</source>
        <favorited>true</favorited>
    </status>
</statuses>
```

##### JSON:
```json
[
    {
      "user":{
         "name":"Owler",
         "screen_name":"owler",
         "id":"65c1421a1897e7840ad8d315",
         "protected":false,
         "profile_image_url":"https://picsum.photos/48/48"
      },
      "text":"what are you doing?",
      "id":20,
      "created_at":"Wed Nov 08 20:48:50 GMT 2023",
      "source":"web",
      "favorited":true
   },
   {
      "user":{
         "name":"Owler",
         "screen_name":"owler",
         "id":"65c1421a1897e7840ad8d315",
         "protected":false,
         "profile_image_url":"https://picsum.photos/48/48"
      },
      "text":"testing the api!",
      "id":10,
      "created_at":"Wed Nov 08 20:47:50 GMT 2023",
      "source":"api",
      "favorited":true
   }
]
```


And a unsuccessful authentication response should look like:


##### XML:
```xml
<hash>
<error>Could not authenticate you.</error>
<request>/v1/favorites.xml</request>
</hash>
```

##### JSON:
```json
{"error": "Could not authenticate you.", "request": "/v1/favorites.json"}
```