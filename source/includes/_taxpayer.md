# Taxpayer Resource
## CreateTaxpayer
```http
POST /{ApiURI}/v1/taxpayers HTTP/1.1
Host: {ApiHost}
x-token: 071ad636-a5c7-4fe1-aac6-60d449ccac6f
Content-Type: application/json
Cache-Control: no-cache

{
	"firstName" : "taxpayerFirstName",
	"lastName" : "taxpayerLastName",
	"email" : "taxpayer@kea.mx",
	"cellphone" : "0000000000",
	"taxpayerType" : "1"
}
```

```shell
curl -X POST -H "x-token: 071ad636-a5c7-4fe1-aac6-60d449ccac6f" -H "Content-Type: application/json" -H "Cache-Control: no-cache" -d '{
	"firstName" : "taxpayerFirstName",
	"lastName" : "taxpayerLastName",
	"email" : "taxpayer@kea.mx",
	"cellphone" : "0000000000",
	"taxpayerType" : "1"
}' "https://{ApiURL}/v1/taxpayers"

```

```php
<?php

$curl = curl_init();

curl_setopt_array($curl, array(
  CURLOPT_PORT => "8080",
  CURLOPT_URL => "https://{ApiURL}/v1/taxpayers",
  CURLOPT_RETURNTRANSFER => true,
  CURLOPT_ENCODING => "",
  CURLOPT_MAXREDIRS => 10,
  CURLOPT_TIMEOUT => 30,
  CURLOPT_HTTP_VERSION => CURL_HTTP_VERSION_1_1,
  CURLOPT_CUSTOMREQUEST => "POST",
  CURLOPT_POSTFIELDS => "{\n\t\"firstName\" : \"taxpayerFirstName\",\n\t\"lastName\" : \"taxpayerLastName\",\n\t\"email\" : \"taxpayer@kea.mx\",\n\t\"cellphone\" : \"0000000000\",\n\t\"taxpayerType\" : \"1\"\n}",
  CURLOPT_HTTPHEADER => array(
    "cache-control: no-cache",
    "content-type: application/json",
    "x-token: 071ad636-a5c7-4fe1-aac6-60d449ccac6f"
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
x-created-at: Mon, 20 Mar 2017 19:53:21 GMT
x-token: 4f0f657f-0f74-4756-b86e-32facf8a35b5
x-updated-at: Mon, 20 Mar 2017 19:53:21 GMT
```

```json
# Body Response
{
  "success": false,
  "error": {
    "code": 1,
    "message": "The email {emailValue} already exist."
  }
}
```

This web service create a new `taxpayer`

### HTTP Request

`POST /v1/taxpayers`

### Header Parameters

Parameters | Required | Type  | Description 
--------- | ------- | ------- | -------
x-token | true | String | client's token
Content-Type | true | String | indicate the media type of the resource

### Body Parameters `TaxpayerRQ Attributes`

Attribute | Required | Type  | Maxlength 
--------- | ------- | ------- | -------
firstName | true | String | 150 chars
lastName | true | String | 150 chars
email | true | String | 250 chars
cellphone | true | String | 10 chars
taxpayerType | true | Int | 

### Exceptions

Code | Name | Message 
--------- | ------- | -------
0000 | EmailExistException |  The email {emailValue} already exist.
0000 | InvalidEmailException | The {emailName} is invalid email address.
0000 | IvalidCellphoneException | The {phoneNumber} is invalid only allow digits.
0000 | InvalidParamException |  The param {paramName} is invalid.
0000 | TaxpayerTypeNotExistsException |  The taxpayer type {taxpayerTypeValue} not exists.
0000 | RequiredParamException | The param {paramName} is required.
0000 | MaxlengthParamException | The maximun length of {paramName} is {maxlengthValue}.