# Authentication





## Login Client ##

```shell
  curl -X POST 
  -H "Content-Type: application/json" 
  -d '{
    "password" : "901482",
    "username" : "fxtWebSite"
  }'
  "https://dev.moneta.kea.mx/v1/auth/login/client"
```

> Success Response:

```json
# Connection Response
{
  "token": "4f0f657f-0f74-4756-b86e-32facf8a35b5",
  "createdAt" : "2017-04-01 20:21:11",
  "updatedAt" : "2017-04-01 20:21:11",
  "expiresIn" : "86400"
}
```

> Error Response:

```json
# Body Response
{
  "error": {
    "code": 1,
    "message": "The client credentials are invalid."
  }
}
```

This web service login a client

### Request

`POST /v1/auth/login/client`

Property | Description
:--------- | :-----------
username | **string** (required, length=150) <br> Nickname of client.
password | **string** (required, length=150) <br> Passpord of client.

### Response

Returns a [`ConnectionRS`](#connectionrs) when all the data were sent correctly, or returns an [`error response`](#errors) if a problem happened.





## Logout Client ##

```shell
  curl -X DELETE 
  -H "Content-Type: application/json" 
  -H "x-token: a0294e07-ea36-4cc6-9295-f866c9e40851"
  "https://dev.moneta.kea.mx/v1/auth/logout/client"
```

> Success Response:

```json
# Connection Response
{
  "token": "4f0f657f-0f74-4756-b86e-32facf8a35b5",
  "createdAt" : "2017-04-01 20:21:11",
  "updatedAt" : "2017-04-01 20:21:11",
  "expiresIn" : "86400"
}
```

> Exception Response:

```json
# Body Response
{
  "error": {
    "code": 5XXX,
    "message": "The client information is invalid."
  }
}
```

This web service logout a client.

### Service Type [`Connection`](#connection-service)

### Request

`DELETE /v1/auth/logout/client`

### Response

Returns a [`ConnectionRS`](#connectionrs) when all the data were sent correctly, or returns an [`error response`](#errors) if a problem happened.





## Login Taxpayer ##

```shell
  curl -X POST 
  -H "Content-Type: application/json" 
  -H "x-token: a0294e07-ea36-4cc6-9295-f866c9e40851"
  -d '{
    "username" : "taxpayer@kea.mx",
    "password" : "taxpayer_password",
    "authenticationType" : "1",
  }'
  "https://dev.moneta.kea.mx/v1/auth/login/taxpayer"
```

> Success Response:

```json
# Session Response
{
  "token": "4f0f657f-0f74-4756-b86e-32facf8a35b5",
  "createdAt" : "2017-04-01 20:21:11",
  "updatedAt" : "2017-04-01 20:21:11",
  "expiresIn" : "86400",
  "userId": "4f0f657f-0f74-4756-b86e-32facf8a35b5"
}
```

> Error Response:

```json
# Body Response
{
  "error": {
    "code": 5XXX,
    "message": "The client credentials are invalid."
  }
}
```

This web service login a taxpayer user.

### Service Type [`Connection`](#connection-service)

### Request

`POST /v1/auth/login/taxpayer`

Property | Description
:--------- | :-----------
username | **string** (required, length=150) <br> Nickname of user.
password | **string** (required, length=1500) <br> If the authentication type is **Moneta** send the **Passpword** otherwise send the access **token**.
[authenticationType](#authentication-type) | **numeric** (required) <br> Authentication type of user account.

### Response

Returns a [`SessionRS`](#sessionrs) when all the data were sent correctly, or returns an [`error response`](#errors) if a problem happened.





## Logout Taxpayer ##

```shell
  curl -X DELETE 
  -H "Content-Type: application/json" 
  -H "x-token: a0294e07-ea36-4cc6-9295-f866c9e40851"
  "https://dev.moneta.kea.mx/v1/auth/logout/taxpayer"
```

> Success Response:

```json
# Session Response
{
  "token": "4f0f657f-0f74-4756-b86e-32facf8a35b5",
  "createdAt" : "2017-04-01 20:21:11",
  "updatedAt" : "2017-04-01 20:21:11",
  "expiresIn" : "86400",
  "userId": "4f0f657f-0f74-4756-b86e-32facf8a35b5"
}
```

> Exception Response:

```json
# Body Response
{
  "error": {
    "code": 5XXX,
    "message": "The client information is invalid."
  }
}
```

This web service logout a Taxpayer user.

### Service Type [`Session`](#session-service)

### Request

`DELETE /v1/auth/logout/taxpayer`

### Response

Returns a [`SessionRS`](#sessionrs) when all the data were sent correctly, or returns an [`error response`](#errors) if a problem happened.





## Request a reset password ##

```shell
  curl -X POST 
  -H "Content-Type: application/json" 
  -H "x-token: a0294e07-ea36-4cc6-9295-f866c9e40851"
  -d '{
    "username" : "taxpayer@kea.mx"
  }'
  "https://dev.moneta.kea.mx/v1/auth/reset-password"
```

> Success Response:

```json
# Session Response
{
  "token": "4f0f657f-0f74-4756-b86e-32facf8a35b5",
  "createdAt" : "2017-04-01 20:21:11",
  "updatedAt" : "2017-04-01 20:21:11",
  "expiresIn" : "86400",
  "userId": "4f0f657f-0f74-4756-b86e-32facf8a35b5"
}
```

> Error Response:

```json
# Body Response
{
  "error": {
    "code": 5XXX,
    "message": "The client credentials are invalid."
  }
}
```

Request a reset password of user.

### Service Type [`Connection`](#connection-service)

### Request

`POST /v1/auth/reset-password`

Property | Description
:--------- | :-----------
username | **string** (required, length=150) <br> Nickname of user.

### Response

Returns a [`ResetPasswordRS`](#resetpasswordrs) when all the data were sent correctly, or returns an [`error response`](#errors) if a problem happened.





## Validate a reset password ##

```shell
  curl -X GET 
  -H "Content-Type: application/json" 
  -H "x-token: a0294e07-ea36-4cc6-9295-f866c9e40851"
  "https://dev.moneta.kea.mx/v1/auth/reset-password?token=a0294e07-ea36-4cc6-9295-f866c9e40938"
```

> Success Response:

```json
# Session Response
{
  "transactionToken": "4f0f657f-0f74-4756-b86e-32facf8a35b5",
  "createdAt" : "2017-04-01 20:21:11",
  "updatedAt" : "2017-04-01 20:21:11",
  "expiresIn" : "86400",
  "userId": "4f0f657f-0f74-4756-b86e-32facf8a35b5"
}
```

> Error Response:

```json
# Body Response
{
  "error": {
    "code": 5XXX,
    "message": "The client credentials are invalid."
  }
}
```

Validate a token of reset password user.

### Service Type [`Connection`](#connection-service)

### Request

`GET /v1/auth/reset-password?token={token}`

### Response

Returns a [`TransactionResetPasswordRS`](#transactionresetpasswordrs) when all the data were sent correctly, or returns an [`error response`](#errors) if a problem happened.





## Reset password ##

```shell
  curl -X PUT 
  -H "Content-Type: application/json" 
  -H "x-token: a0294e07-ea36-4cc6-9295-f866c9e40851"
  -d '{
    "transactionToken" : "a0294e07-ea36-4cc6-9295-f866c9e40851",
    "password" : "new_taxpayer_password"
  }'
  "https://dev.moneta.kea.mx/v1/auth/reset-password"
```

> Success Response:

```json
# Session Response
{
  "token": "4f0f657f-0f74-4756-b86e-32facf8a35b5",
  "createdAt" : "2017-04-01 20:21:11",
  "updatedAt" : "2017-04-01 20:21:11",
  "expiresIn" : "86400",
  "userId": "4f0f657f-0f74-4756-b86e-32facf8a35b5"
}
```

> Error Response:

```json
# Body Response
{
  "error": {
    "code": 5XXX,
    "message": "The client credentials are invalid."
  }
}
```

Reset password of user.

### Service Type [`Connection`](#connection-service)

### Request

`PUT /v1/auth/reset-password`

Property | Description
:--------- | :-----------
transactionToken | **string** (required, length=36) <br> Transaction Token of reset password.
password | **string** (required, length=150) <br> The new password of user.


### Response

Returns a [`ResetPasswordRS`](#resetpasswordrs) when all the data were sent correctly, or returns an [`error response`](#errors) if a problem happened.





## Login Accountant ##





## Logout Accountant ##





## Login Manager ##





## Logout Manager ##





## Begin Transaction ##

```shell
  curl -X POST 
  -H "Content-Type: application/json" 
  -H "x-token: a0294e07-ea36-4cc6-9295-f866c9e40851"
  "https://dev.moneta.kea.mx/v1/auth/begin-transaction"
```

> Success Response:

```json
# Transaction Response
{
  "token": "4f0f657f-0f74-4756-b86e-32facf8a35b5",
  "createdAt" : "2017-04-01 20:21:11",
  "updatedAt" : "2017-04-01 20:21:11",
  "expiresIn" : "86400",
  "userId": "4f0f657f-0f74-4756-b86e-32facf8a35b5"
}
```

> Error Response:

```json
# Body Response
{
  "error": {
    "code": 5XXX,
    "message": "The client credentials are invalid."
  }
}
```

This web service begin a transaction token.

### Service Type [`Session`](#session-service)

### Request

`POST /v1/auth/begin-transaction`

### Response

Returns a [`TransactionRS`](#transactionrs) when all the data were sent correctly, or returns an [`error response`](#errors) if a problem happened.






## End Transaction ##

```shell
  curl -X DELETE 
  -H "Content-Type: application/json" 
  -H "x-token: a0294e07-ea36-4cc6-9295-f866c9e40851"
  "https://dev.moneta.kea.mx/v1/auth/end-transaction"
```

> Success Response:

```json
# Transaction Response
{
  "token": "4f0f657f-0f74-4756-b86e-32facf8a35b5",
  "createdAt" : "2017-04-01 20:21:11",
  "updatedAt" : "2017-04-01 20:21:11",
  "expiresIn" : "86400",
  "userId": "4f0f657f-0f74-4756-b86e-32facf8a35b5"
}
```

> Error Response:

```json
# Body Response
{
  "error": {
    "code": 5XXX,
    "message": "The client credentials are invalid."
  }
}
```

This web service end a transaction token.

### Service Type [`Transaction`](#transaction-service)

### Request

`DELETE /v1/auth/end-transaction`

### Response

Returns a [`TransactionRS`](#transactionrs) when all the data were sent correctly, or returns an [`error response`](#errors) if a problem happened.





## Validate Connection ##

```shell
  curl -X GET 
  -H "Content-Type: application/json" 
  -H "x-token: a0294e07-ea36-4cc6-9295-f866c9e40851"
  "https://dev.moneta.kea.mx/v1/auth/validate/connection"
```

> Success Response:

```json
# Connection Response
{
  "token": "4f0f657f-0f74-4756-b86e-32facf8a35b5",
  "createdAt" : "2017-04-01 20:21:11",
  "updatedAt" : "2017-04-01 20:21:11",
  "expiresIn" : "86400"
}
```

> Exception Response:

```json
# Body Response
{
  "error": {
    "code": 5XXX,
    "message": "The client information is invalid."
  }
}
```

This web service validate a connection token.

### Service Type [`Connection`](#connection-service)

### Request

`GET /v1/auth/validate/connection`

### Response

Returns a [`ConnectionRS`](#connectionrs) when all the data were sent correctly, or returns an [`error response`](#errors) if a problem happened.





## Validate Session ##

```shell
  curl -X GET 
  -H "Content-Type: application/json" 
  -H "x-token: a0294e07-ea36-4cc6-9295-f866c9e40851"
  "https://dev.moneta.kea.mx/v1/auth/validate/session"
```

> Success Response:

```json
# Connection Response
{
  "token": "4f0f657f-0f74-4756-b86e-32facf8a35b5",
  "createdAt" : "2017-04-01 20:21:11",
  "updatedAt" : "2017-04-01 20:21:11",
  "expiresIn" : "86400",
  "userId" : "4f0f657f-0f74-4756-b86e-32facf8a35b5"
}
```

> Exception Response:

```json
# Body Response
{
  "error": {
    "code": 5XXX,
    "message": "The client information is invalid."
  }
}
```

This web service validate a session token.

### Service Type [`Session`](#session-service)

### Request

`GET /v1/auth/validate/session`

### Response

Returns a [`SessionRS`](#sessionrs) when all the data were sent correctly, or returns an [`error response`](#errors) if a problem happened.





## Validate Transaction ##

```shell
  curl -X GET 
  -H "Content-Type: application/json" 
  -H "x-token: a0294e07-ea36-4cc6-9295-f866c9e40851"
  "https://dev.moneta.kea.mx/v1/auth/validate/transaction"
```

> Success Response:

```json
# Connection Response
{
  "token": "4f0f657f-0f74-4756-b86e-32facf8a35b5",
  "createdAt" : "2017-04-01 20:21:11",
  "updatedAt" : "2017-04-01 20:21:11",
  "expiresIn" : "86400",
  "userId" : "4f0f657f-0f74-4756-b86e-32facf8a35b5"
}
```

> Exception Response:

```json
# Body Response
{
  "error": {
    "code": 5XXX,
    "message": "The client information is invalid."
  }
}
```

This web service validate a transaction token.

### Service Type [`Transaction`](#transaction-service)

### Request

`GET /v1/auth/validate/transaction`

### Response

Returns a [`TransactionRS`](#transactionrs) when all the data were sent correctly, or returns an [`error response`](#errors) if a problem happened.





