---
title: /account/verify_credentials
layout: default
---
# /account/verify_credentials

To verify account credentials. Authentication is required.

## Responses

### HTTP Status
- ```200``` - Authenticated succesfully
- ```401``` - Invalid login details

### Body

#### Fields:
* ```success``` (string) [optional]: Message indicating the autentication was successful.
* ```error``` (string) [optional]: Message indicating the autentication was unsuccessful, or other errors that could occur.
* ```request``` (string): Request endpoint

A successful authentication response should look like this:

##### XML:
```xml
<hash>
<success>Authenticated succesfully.</success>
<request>/v1/account/verify_credentials.xml</request>
</hash>
```

##### JSON:
```json
{"success": "Authenticated succesfully.", "request": "/v1/account/verify_credentials.json"}
```


And a unsuccessful authentication response should look like:


##### XML:
```xml
<hash>
<error>Could not authenticate you.</error>
<request>/v1/account/verify_credentials.xml</request>
</hash>
```

##### JSON:
```json
{"error": "Could not authenticate you.", "request": "/v1/account/verify_credentials.json"}
```