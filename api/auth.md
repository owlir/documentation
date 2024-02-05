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

When making requests to the Owler API, include the Basic Authentication credentials in the Authorization header of your HTTP request. Here's an example using JavaScript:

```javascript
var endpoint = 'https://api.owler.cloud/account/verify_credentials.json';
xhr.open('GET', url, true);

var credentials = btoa(username + ':' + password);
xhr.setRequestHeader('Authorization', 'Basic ' + credentials)

xhr.onload = function () {
if (xhr.status == 401) {
    alert('Invalid username or password!');
} else if (xhr.status == 200) {
    alert('Logged successfully.');
} 
};

xhr.send(data);
```