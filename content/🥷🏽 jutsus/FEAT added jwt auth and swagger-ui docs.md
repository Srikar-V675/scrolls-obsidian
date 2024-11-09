---
date: 2024-11-09 09:14
tags:
  - pr
project: "[[SyncWise]]"
link: 
branch: auth
publish: true
---

**PROJECT:** [[SyncWise]]

**LINK:** 

**BRANCH:** auth

## Changes 
- slight changes in models.
- made changes in settings to enable simple jwt auth
- added urls to `urls.py` for token creation and refresh.
- created a `serialzer` for User model to test the JWT tokens.
- created a `viewset` for User model for the same case.
- added some models to admin site to help development(NOTE: for only development).
- added swagger-ui `api docs` for easier API requests(I personally just prefer it)

## Description

### JWT Auth 
Just lookup JWT Auth online you would understand what it is. It is basically a token based authentication with `access` and `refresh` tokens.

**In our app,** 
You should be able to access tokens endpoints at: `/api/token/`. You can enter `username` and `password` for an existing user. 

The endpoint will return `refresh` and `access` tokens that look like this,

```json
{
	`refresh`: `...`,
	'access': `...`
}
```

The `access` token must be added as an `Authorization` header for every request that must be Authenticated. The request should look like this:

```
POST http://0.0.0.0:8050/api/users/
Authorization: Bearer <access-token>
content-type: application/json
data
{
  "username": "Test",
  "password": "test"
}
```

If you receive a response telling that access token expired then you can use the `refresh` token to refresh the token. You should send the request to endpoint: `/api/token/refresh/`.It should return a new `access` token:

```json
{
	'access': '...'
}
```

> [!note]
> You can access the API docs at endpoint: `/api/schema/swagger-ui`. You'll know what it is when you access it.

