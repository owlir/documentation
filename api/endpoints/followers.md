---
title: /statuses/followers
layout: default
parent: Endpoints
---
# /statuses/followers

Get the 100 last users you're following or are friends with. Authentication is required.
## Responses

### HTTP Status
- `200`
- `401` - Authentication was unsuccessful
- `400` 
### Body

#### Fields:
* `user` (User object) with a extra field: `follow_id` (ObjectId str)

A successful response should look like this:

##### XML:
```xml
<?xml version="1.0" encoding="UTF-8" ?>
<users>
    <user>
        <follow_id>65b80eb859920c6d06e291d7</follow_id>
        <id>65354165a9fd5b661a33732a</id>
        <name>Owler</name>
        <screen_name>owler</screen_name>
        <profile_image_url>https://picsum.photos/48/48</profile_image_url>
    </user>
</users>
```

##### JSON:
```json
[
    {
        "follow_id": "65b80eb859920c6d06e291d7",
        "id": "65354165a9fd5b661a33732a",
        "name": "Owler",
        "screen_name": "owler",
        "profile_image_url": "https://picsum.photos/48/48"
    }
]
```


And a unsuccessful response should look like:


##### XML:
```xml
<hash>
<error>Could not authenticate you.</error>
<request>/v1/statuses/home_timeline.xml</request>
</hash>
```

##### JSON:
```json
{"error": "Could not authenticate you.", "request": "/v1/statuses/home_timeline.json"}
```