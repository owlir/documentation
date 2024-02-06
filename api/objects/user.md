---
title: User Object
layout: default
parent: Objects
---
# User

Get the following timeline. Authentication is required.
## Request
**HTTP Methods**: GET, POST
### Fields:
* ```count``` (int) [optional]: How many updates you get in the response (until 40, default is 10)
* ```page``` (int) [optional]: This field specifies the page number of the results you want to retrieve. (minimum 1)
* ```full``` (boolean) [optional]: When "true" is set, it should return more information about the updates, for example when the user is replying to a status a ```reply``` field should be set, and other fields, mentioned below.

**Example:** ```user```

## Responses

### HTTP Status
- ```200``` - Successfully 
- ```400``` - Validation error, or other errors
- ```401``` - Invalid login details

### Body

In a successful response, it should return the following fields:

#### Fields:
* ```user``` (user object)
* ```text``` (string)
* ```created_at``` (timestamp): When the status was created.
* ```source``` (string): App used for creating the status.
#### The following fields should only appear when full is set to true:
* ```favorited``` (bool): If you favorited this update or not.
* ```reply``` (object) [optional] with ```reply.user``` (user object) [optional] and ```reply.id```

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
        <text>testing the api!</text>
        <id>30</id>
        <created_at>Wed Nov 08 20:47:50 GMT 2023</created_at>
        <source>web (legacy)</source>
        <favorited>false</favorited>
    </status>
    <status>
        <user>
            <name>alguem</name>
            <screen_name>alguem</screen_name>
            <id>65c14223115d030584d3d2b8</id>
            <protected>false</protected>
            <profile_image_url>https://picsum.photos/48/48</profile_image_url>
        </user>
        <text>ola amigos!</text>
        <id>20</id>
        <created_at>Thu Nov 02 22:50:40 GMT 2023</created_at>
        <source>web (legacy)</source>
        <favorited>false</favorited>
    </status>
    <status>
        <user>
            <name>someone</name>
            <screen_name>someone</screen_name>
            <id>65c14229cf25e514d7a064d3</id>
            <protected>false</protected>
            <profile_image_url>https://picsum.photos/48/48</profile_image_url>
        </user>
        <text>hello friends!</text>
        <id>10</id>
        <created_at>Thu Nov 02 16:40:50 GMT 2023</created_at>
        <source>web (legacy)</source>
        <favorited>false</favorited>
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
      "text":"testing the api!",
      "id":1960,
      "created_at":"Wed Nov 08 20:47:50 GMT 2023",
      "source":"web (legacy)",
      "favorited":false
   }
]
```


And a unsuccessful authentication response should look like:


##### XML:
```xml
<hash>
<error>Could not authenticate you.</error>
<request>user.xml</request>
</hash>
```

##### JSON:
```json
{"error": "Could not authenticate you.", "request": "user.json"}
```