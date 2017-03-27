# Authentication





## Login Client ##

```shell
  curl -X POST 
  -H "Content-Type: application/json" 
  "https://{ApiURL}/v1/auth/login-client?password=901482&username=fxtWebSite"
```

> Success Response:

```text
# Status
Status: 200

# Header Response
x-created-at: Mon, 20 Mar 2017 19:53:21 GMT
x-token: 4f0f657f-0f74-4756-b86e-32facf8a35b5
x-updated-at: Mon, 20 Mar 2017 19:53:21 GMT
```

```json
# Body Response
{
  "success": true
}
```

> Exception Response:

```text
# Status
Status: {exception.code}

# Header Response
```

```json
# Body Response
{
  "success": false,
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
  curl -X GET 
  -H "Content-Type: application/json" 
  -H "x-token: a0294e07-ea36-4cc6-9295-f866c9e40851"
  "https://{ApiURL}/v1/auth/logout-client"
```

> Success Response:

```text
# Status
Status: 200

# Header Response
x-created-at: Mon, 20 Mar 2017 19:53:21 GMT
x-token: 4f0f657f-0f74-4756-b86e-32facf8a35b5
x-updated-at: Mon, 20 Mar 2017 19:53:21 GMT
```

```json
# Body Response
{
  "success": true
}
```

> Exception Response:

```text
# Status
Status: {exception.code}

# Header Response
```

```json
# Body Response
{
  "success": false,
  "error": {
    "code": 3,
    "message": "The client information is invalid."
  }
}
```

This web service logout a client.

### Service Type [`Connection`](#connection-service)

### Request

`GET /v1/auth/logout/client`

### Response

Returns a [`ConnectionRS`](#connectionrs) when all the data were sent correctly, or returns an [`error response`](#errors) if a problem happened.





## Login Taxpayer ##
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
This web service logout a Taxpayer user.

### Service Type [`Session`](#session-service)

### Request

`GET /v1/auth/logout/taxpayer`

### Response

Returns a [`SessionRS`](#sessionrs) when all the data were sent correctly, or returns an [`error response`](#errors) if a problem happened.





## Request a reset password ##

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

Validate a token of reset password user.

### Service Type [`Connection`](#connection-service)

### Request

`GET /v1/auth/reset-password?token={token}`

### Response

Returns a [`TransactionResetPasswordRS`](#transactionresetpasswordrs) when all the data were sent correctly, or returns an [`error response`](#errors) if a problem happened.





## Reset password ##

Reset password of user.

### Service Type [`Connection`](#connection-service)

### Request

`PUT /v1/auth/reset-password`

Property | Description
:--------- | :-----------
transactionToken | **string** (required, length=36) <br> Transaction Token of reset password.
oldPassword | **string** (required, length=150) <br> Old pasword of user.
newPassword | **string** (required, length=150) <br> New password of user.


### Response

Returns a [`ResetPasswordRS`](#resetpasswordrs) when all the data were sent correctly, or returns an [`error response`](#errors) if a problem happened.





## Login Accountant ##





## Logout Accountant ##





## Login Manager ##





## Logout Manager ##





## Validate Connection ##

This web service validate a connection token.

### Service Type [`Connection`](#connection-service)

### Request

`GET /v1/auth/validate/connection`

### Response

Returns a [`ConnectionRS`](#connectionrs) when all the data were sent correctly, or returns an [`error response`](#errors) if a problem happened.




## Validate Session ##

This web service validate a session token.

### Service Type [`Session`](#session-service)

### Request

`GET /v1/auth/validate/session`

### Response

Returns a [`SessionRS`](#sessionrs) when all the data were sent correctly, or returns an [`error response`](#errors) if a problem happened.





## Validate Transaction ##

This web service validate a transaction token.

### Service Type [`Transaction`](#transaction-service)

### Request

`GET /v1/auth/validate/transaction`

### Response

Returns a [`TransactionRS`](#transactionrs) when all the data were sent correctly, or returns an [`error response`](#errors) if a problem happened.





## Begin Transaction ##

This web service begin a transaction token.

### Service Type [`Session`](#session-service)

### Request

`GET /v1/auth/begin-transaction`

### Response

Returns a [`TransactionRS`](#transactionrs) when all the data were sent correctly, or returns an [`error response`](#errors) if a problem happened.






## End Transaction ##

This web service end a transaction token.

### Service Type [`Transaction`](#transaction-service)

### Request

`GET /v1/auth/end-transaction`

### Response

Returns a [`TransactionRS`](#transactionrs) when all the data were sent correctly, or returns an [`error response`](#errors) if a problem happened.





