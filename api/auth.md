---
title: Authentication
layout: default
---

# Authentication

All of the methods (except for the public timeline) require user authentication via Basic Auth.

## Basic Auth Credentials

- **Username:** Your username or email address registered on Owler.
- **Password:** Your Owler account password.

## Making Requests

When making requests to the Owler API, include the Basic Authentication credentials in the Authorization header of your HTTP request. Here's an example using cURL:

```bash
curl -X GET \
  -H "Authorization: Basic ENCODED_CREDENTIALS" \
  https://api.owler.cloud/v1/verify_credentials.json```

ENCODED_CREDENTIALS 