# Authentication

## LoginClient

```http
  POST /{ApiUri}/v1/auth/login-client?password=901482&username=fxtWebSite HTTP/1.1
  Host: {domainApi}
  Content-Type: application/json
  Cache-Control: no-cache
```

```shell
  curl -X POST -H "Content-Type: application/json" 
  "https://{ApiURL}/v1/auth/login-client?password=901482&username=fxtWebSite"
```

```php
  <?php

    $curl = curl_init();

    curl_setopt_array($curl, array(
      CURLOPT_PORT => "8080",
      CURLOPT_URL => "https://{ApiUrl}/v1/auth/login-client?password=901482&username=fxtWebSite",
      CURLOPT_RETURNTRANSFER => true,
      CURLOPT_ENCODING => "",
      CURLOPT_MAXREDIRS => 10,
      CURLOPT_TIMEOUT => 30,
      CURLOPT_HTTP_VERSION => CURL_HTTP_VERSION_1_1,
      CURLOPT_CUSTOMREQUEST => "POST",
      CURLOPT_HTTPHEADER => array(
        "cache-control: no-cache",
        "content-type: application/json",
      ),
    ));

    $response = curl_exec($curl);
    $err = curl_error($curl);

    curl_close($curl);

    if ($err) {
      echo "cURL Error #:" . $err;
    } else {
      echo $response;
    }

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

```http
  GET /{ApiUri}/v1/auth/logout-client HTTP/1.1
  Host: {domainApi}
  x-token: a0294e07-ea36-4cc6-9295-f866c9e40851
  Cache-Control: no-cache
```

```shell
  curl -X GET 
  -H "Content-Type: application/json" 
  -H "x-token: a0294e07-ea36-4cc6-9295-f866c9e40851"
  "https://{ApiURL}/v1/auth/logout-client"
```

```php
  <?php

    $curl = curl_init();

    curl_setopt_array($curl, array(
      CURLOPT_PORT => "8080",
      CURLOPT_URL => "https://{ApiUrl}/v1/auth/logout-client",
      CURLOPT_RETURNTRANSFER => true,
      CURLOPT_ENCODING => "",
      CURLOPT_MAXREDIRS => 10,
      CURLOPT_TIMEOUT => 30,
      CURLOPT_HTTP_VERSION => CURL_HTTP_VERSION_1_1,
      CURLOPT_CUSTOMREQUEST => "GET",
      CURLOPT_HTTPHEADER => array(
        "cache-control: no-cache",
        "content-type: application/json",
        "x-token: a0294e07-ea36-4cc6-9295-f866c9e40851"
      ),
    ));

    $response = curl_exec($curl);
    $err = curl_error($curl);

    curl_close($curl);

    if ($err) {
      echo "cURL Error #:" . $err;
    } else {
      echo $response;
    }

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