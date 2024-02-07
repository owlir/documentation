---
title: Making requests
layout: default
nav_order: 2
---

# Making requests

All queries to the Owler API must be served over HTTPS and need to be presented in this form:
- ```https://api.owler.cloud/v1/{ENDPOINT}.{EXTENSION}```

We also have a secondary domain. You should only use it in case the main one is down:

- ```https://api.owler.top/v1/{ENDPOINT}.{EXTENSION}```

You should also respect the rate limit for each endpoint. Most endpoints have 100 per hour request rate limit. The recommended is to make as little requests as possible, so caching is needed, in case you're creating a client.

## Extension

We only support XML and JSON as file types. Some endpoints are exceptions, though, accepting RSS only as file type.