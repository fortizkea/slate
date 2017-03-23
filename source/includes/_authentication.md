# Authentication

## LoginClient

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

### HTTP Request

`POST /v1/auth/login-client`

### Query Parameters

Parameters | Required | Type  | Description 
--------- | ------- | ------- | -------
username | true | String | client's username
password | true | String | client's password

### Exceptions

Code | Name | Message 
--------- | ------- | -------
0000 | InvalidClientCredentialsException |  The client credentials are invalid.
0000 | MaxClientConnectionException | Too many client connections..
0000 | InvalidClientConnectionException | The client information is invalid.

## LogoutClient

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

### HTTP Request

`GET /v1/auth/logout-client`

### Header Parameters

Parameters | Required | Type  | Description 
--------- | ------- | ------- | -------
x-token | true | String | client's token

### Exceptions

Code | Name | Message 
--------- | ------- | -------
0000 | InvalidClientConnectionException |  The client information is invalid.