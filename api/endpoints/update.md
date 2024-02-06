---
title: /statuses/update
layout: default
parent: Endpoints
---
# /statuses/update

Authentication is required.

## Request
**HTTP Methods**: POST
### Fields:
* `status` (string): Update text
* `source` (string) [optional]: You should specify which application this update is coming from (eg. owleriffic)

**Example:** a POST request to `/v1/statuses/update.xml?status=testing from api docs!`
## Responses

### HTTP Status
- `200` - Success
- `400` - Validation error
- `401` - Invalid login details

### Body

#### Fields:
* `success` (string) [optional]: Message indicating the autentication was successful.
* `error` (string) [optional]: Message indicating the autentication was unsuccessful, or other errors that could occur.
* `request` (string): Request endpoint

A successful response should look like this:

##### XML:
```xml
<hash>
<success>Status sent</success>
<request>/v1/statuses/update.xml</request>
</hash>
```

##### JSON:
```json
{
    "success": "Status sent",
    "request": "/v1/statuses/update.json"
}
```


And a unsuccessful response should look like:


##### XML:
```xml
<hash>
<error>You need to specify status</error>
<request>/v1/statuses/update.json</request>
</hash>
```

##### JSON:
```json
{
    "error": "You need to specify status",
    "request": "/v1/statuses/update.json"
}
```