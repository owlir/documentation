---
title: User Object
layout: default
parent: Objects
---
# User
Some fields can be null or simply be not specified on the User object. Example, in the timeline, only these fields should appear:
*   `id`
*   `name`
*   `screen_name`
*   `protected`
*   `profile_image_url`

#### All fields:

*   `id` (ObjectId string)
*   `name` (string)
*   `screen_name` (string)
*   `location` (string) [nullable]
*   `description` (string) [nullable]: Bio provided by the user.
*   `profile_image_url` (string) [nullable]: The URL of the user's profile image.
*   `url` (string) [nullable]: The URL associated with the user's profile.
*   `protected` (bool): Indicates if the user's profile is protected (true/false).
*   `role` (int) (Role object)
*   `followers_count`: The number of followers the user has.
*   `following_count`: The number of users the user is following.
*   `updates_count`: The number of updates made by the user.
*   `custom_design` [nullable] [Custom Design object]
*   `recently` (string) [nullable]: The user's most recent update.

Below do only appear if you're trying to access the same user that is authenticated using the `/users` endpoint.
*   `friend_requests_count`: The number of friend requests the user has received.
*   `direct_messages_count`: The number of direct messages the user has received.

*   `email`: The email associated with the user.
*   `email_verified` (bool): Indicates if the user's email is verified (true/false).
*   `time_zone`: Tz timezone.
*   `lang`: The language code