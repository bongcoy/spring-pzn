# User API Spec

## Register User

Endpoint: POST /api/users

Request Body:

```json
{
  "username": "bongcoy",
  "password": "rahasia",
  "name": "Bongcoy Aye"
}
```

Response Body (success):

```json
{
  "data": "OK"
}
```

Response Body (failed):

```json
{
  "errors": "Username must not blank!"
}
```

## Login User

Endpoint: POST /api/auth/login

Request Body:

```json
{
  "username": "bongcoy",
  "password": "rahasia"
}
```

Response Body (success):

```json
{
  "data": {
    "token": "TOKEN",
    "expiredAt": 123123123 // miliseconds
  }
}
```

Response Body (failed):

```json
{
  "errors": "Username or password wrong!"
}
```

## Get User

Endpoint: GET /api/users/current

Response Body (success):

```json
{
  "data": {
    "username": "bongcoy",
    "name": "Bongcoy Aye"
  }
}
```

Response Body (failed):

```json
{
  "errors": "Unauthorized"
}
```

## Update User

Endpoint: PATCH /api/users/current

Response Body (success):

```json
{
  "name": "Bongcoy Aye", // parsial
  "password": "new password" // parsial
}
```

Response Body (failed):

```json
{
  "errors": "Unauthorized"
}
```

## Logout User