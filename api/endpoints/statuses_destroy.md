---
title: /statuses/destroy
layout: default
parent: Endpoints
---
# /statuses/destroy/{sid}

Authentication is required.
- `sid`: Statuses's `id`
## Request
**HTTP Methods**: POST

**Example:** a POST request to `/v1/statuses/destroy/10.xml`
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
<success>Status deleted successfully</success>
<request>/v1/statuses/destroy/10.xml</request>
</hash>
```

##### JSON:
```json
{
    "success": "Status deleted successfully",
    "request": "/v1/statuses/destroy/10.json"
}
```


And a unsuccessful response should look like:


##### XML:
```xml
<hash>
<error>Status doesn't exist or you don't have permission to delete it</error>
<request>/v1/statuses/destroy/10.json</request>
</hash>
```

##### JSON:
```json
{
    "error": "Status doesn't exist or you don't have permission to delete it",
    "request": "/v1/statuses/destroy/10.json"
}
```