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

`POST /v1/auth/login-client`

Send in the body params the [`LoginClientRQ`](#loginclientrq) object.

### Response

The service response the [`Response`](#responseobj) object.

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

This web service logout a client

### Service Type `ConnectionService`
Read the [`ConnectionService`](#connectionservice) requierements.

### Request

`GET /v1/auth/logout-client`

### Response

The service response the [`Response`](#responseobj) object.


## Login Taxpayer ##
## Logout Taxpayer ##
## Reset Password Taxpayer ##

## Login Accountant ##
## Logout Accountant ##
## Reset Password Accountant ##

## Login Manager ##
## Logout Manager ##
## Reset Password Manager ##

## Validate Connection ##
## Validate Session ##
## Validate Transaction ##






