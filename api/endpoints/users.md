---
title: /users
layout: default
parent: Endpoints
---
# /users

There's these endpoints you can use for getting user information:
* `/users/show` - Get the logged user info. Authentication is required.
* `/users/{id}` and `/users/show/{id}` - Get the user info. ID can be the user id or screen name.
## Responses

### HTTP Status
- `200` - User info was successfully obtained
- `404` - User not found (on `/users/show`, it indicates the authentication was unsuccessful)
- `400` 
### Body

#### Fields:
* `user` (User object)

A successful response should look like this:

##### XML:
```xml
<user>
    <id>65b8463bdc27c12a62c15ac5</id>
    <name>test</name>
    <screen_name>test</screen_name>
    <location/>
    <description/>
    <profile_image_url>
    https://picsum.photos/48/48
    </profile_image_url>
    <url/>
    <protected>false</protected>
    <role>0</role>
    <followers_count>1</followers_count>
    <following_count>1</following_count>
    <updates_count>7</updates_count>
    <custom_design>
        <screen_name_color>#ff2929</screen_name_color>
        <text_color>#2975ff</text_color>
        <link_color>#29ff72</link_color>
        <sidebar_border_color>#ff292e</sidebar_border_color>
        <sidebar_color>#ffad29</sidebar_color>
        <background_color>#ff29a0</background_color>
        <background_position/>
        <background_repeat/>
        <background_attachment/>
        <background_size/>
    </custom_design>
    <recently>@test olá</recently>
</user>
```

##### JSON:
```json
{
  "id": "65b8463bdc27c12a62c15ac5",
  "name": "test",
  "screen_name": "test",
  "location": null,
  "description": null,
  "profile_image_url": "https://picsum.photos/48/48",
  "url": null,
  "protected": false,
  "role": 0,
  "followers_count": 1,
  "following_count": 1,
  "updates_count": 7,
  "custom_design": {
    "screen_name_color": "#ff2929",
    "text_color": "#2975ff",
    "link_color": "#29ff72",
    "sidebar_border_color": "#ff292e",
    "sidebar_color": "#ffad29",
    "background_color": "#ff29a0",
    "background_position": "",
    "background_repeat": "",
    "background_attachment": "",
    "background_size": ""
  },
  "recently": "@test olá"
}
```


And a unsuccessful response should look like:


##### XML:
```xml
<hash>
    <error>User doesn't exist</error>
    <request>/api/v1/users/show.xml</request>
</hash>
```

##### JSON:
```json
{"error": "User doesn't exist", "request": "/v1/users/show.json"}
```