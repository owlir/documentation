---
title: /help/test
layout: default
---
# /help/test

Useful for checking server status

## Responses

### HTTP Status
- ```200``` - Server is working
- ```404``` - Server is not currently available 
- ```400``` or  ```500``` - Server is down, or having problems

### Body

### XML:
```xml
<hash>
<success>true</success>
<request>/v1/help/test.xml</request>
</hash>
```

### JSON:
```json
{"success": true, "request": "/v1/help/test.json"}
```