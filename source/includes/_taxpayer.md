# Taxpayers





## Create Taxpayer ##

```shell
curl -X POST 
-H "Content-Type: application/json"
-H "x-token: 071ad636-a5c7-4fe1-aac6-60d449ccac6f" 
-d '{
	"firstName" : "First name of user",
	"lastName" : "Last name of user",
	"email" : "taxpayer@kea.mx",
	"mobile" : "0000000000",
	"authenticationType" : 1
}' 
"https://dev.moneta.kea.mx/v1/taxpayers"

```
> Success Response:

```json
# Taxpayer Response
{
  "id" : "5",
  "userId" : "4f0f657f-0f74-4756-b86e-32facf8a35b5",
  "firstName" : "Fidel",
  "lastName" : "Ortiz Peña",
  "email" : "taxpayer@kea.mx",
  "mobile" : "0000000000",
  "birthdate" : null,
  "active" : true,
  "avatar" : "",
  "curp" : null,
  "workflowEntry" : {},
  "gender" : {},
  "taxInformation" : {},
  "createdAt" : "2017-04-01 20:21:11",
  "updatedAt" : "2017-04-01 20:21:11",
  "deletedAt" : null
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

Create a new `taxpayer`

### Service Type [`Connection`](#connection-service)

### Request

`POST /v1/taxpayers`

Property | Description
:--------- | :-----------
firstName | **string** (required, length=50) <br> First name of taxpayer.
lastName | **string** (required, length=50) <br> Last name of taxpayer.
email | **string** (required, length=150) <br> Email of taxpayer.
mobile | **string** (required, length=16) <br> Mobile number of taxpayer.
[authenticationType](#authentication-type) | **numeric** (required) <br> Authentication type of taxpayer.

### Response

Returns a [`TaxpayerRS`](#taxpayerrs) when all the data were sent correctly, or returns an [`error response`](#errors) if a problem happened.





## Read Taxpayer ##

```shell
curl -X GET 
-H "Content-Type: application/json"
-H "x-token: 071ad636-a5c7-4fe1-aac6-60d449ccac6f"
"https://dev.moneta.kea.mx/v1/taxpayers/5"

```
> Success Response:

```json
# Taxpayer Response
{
  "id" : "5",
  "userId" : "4f0f657f-0f74-4756-b86e-32facf8a35b5",
  "firstName" : "Fidel",
  "lastName" : "Ortiz Peña",
  "email" : "taxpayer@kea.mx",
  "mobile" : "0000000000",
  "birthdate" : null,
  "active" : true,
  "avatar" : "/img/default-avatar.jpg",
  "curp" : null,
  "workflowEntry" : {},
  "gender" : {},
  "taxInformation" : {},
  "createdAt" : "2017-04-01 20:21:11",
  "updatedAt" : "2017-04-01 20:21:11",
  "deletedAt" : null
}
```

> Error Response:

```json
# Body Response
{
  "error": {
    "code": 5XXX,
    "message": "The taxpayer not found."
  }
}
```

Get a `taxpayer` by Id.

### Service Type [`Session`](#session-service)

### Request

`GET /v1/taxpayers/{taxpayerId}`

Query Params |  Description 
:--------- | :-------
taxpayerId | **numeric** (required) <br> Taxpayer's Identifier

### Response

Returns a [`TaxpayerRS`](#taxpayerrs) when all the data were sent correctly, or returns an [`error response`](#errors) if a problem happened.





## Update Taxpayer ##

```shell
curl -X PUT 
-H "Content-Type: application/json"
-H "x-token: 071ad636-a5c7-4fe1-aac6-60d449ccac6f" 
-d '{
  "firstName" : "Fidel",
  "lastName" : "Ortiz Peña",
  "mobile" : "0000000000",
  "birthdate" : "1990-02-20",
  "curp" : "OIPF900220HOCRXD07",
  "genderId" : 1,
}' 
"https://dev.moneta.kea.mx/v1/taxpayers/5"

```
> Success Response:

```json
# Taxpayer Response
{
  "id" : "5",
  "userId" : "4f0f657f-0f74-4756-b86e-32facf8a35b5",
  "firstName" : "Fidel",
  "lastName" : "Ortiz Peña",
  "email" : "taxpayer@kea.mx",
  "mobile" : "0000000000",
  "birthdate" : "1990-02-20",
  "active" : true,
  "avatar" : "/img/default-avatar.jpg",
  "curp" : "OIPF900220HOCRXD07",
  "workflowEntry" : {},
  "gender" : {
    "id" : 1,
    "name" : "Male"
  },
  "taxInformation" : {},
  "createdAt" : "2017-04-01 20:21:11",
  "updatedAt" : "2017-04-01 20:21:11",
  "deletedAt" : null
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

Update a `taxpayer` by Id.

### Service Type [`Session`](#session-service)

### Request

`PUT /v1/taxpayers/{taxpayerId}`

Property | Description
:--------- | :-----------
firstName | **string** (required, length=50) <br> First name of profile.
lastName | **string** (required, length=50) <br> Last name of profile.
mobile | **string** (required, length=16) <br> Mobile number of profile.
birthdate | **date** (optional) <br> Birthdate of profile.
curp | **string** (optional, length=18) <br> Unique population registry code of profile.
[genderId](#gender-type) | **numeric** (optional) <br> Gender of profile.

### Response

Returns a [`TaxpayerRS`](#taxpayerrs) when all the data were sent correctly, or returns an [`error response`](#errors) if a problem happened.





## Delete Taxpayer ##

```shell
curl -X DELETE 
-H "Content-Type: application/json"
-H "x-token: 071ad636-a5c7-4fe1-aac6-60d449ccac6f"
"https://dev.moneta.kea.mx/v1/taxpayers/5"

```
> Success Response:

```json
# Taxpayer Response
{
  "id" : "5",
  "userId" : "4f0f657f-0f74-4756-b86e-32facf8a35b5",
  "firstName" : "Fidel",
  "lastName" : "Ortiz Peña",
  "email" : "taxpayer@kea.mx",
  "mobile" : "0000000000",
  "birthdate" : "1990-02-20",
  "active" : true,
  "avatar" : "/img/default-avatar.jpg",
  "curp" : "OIPF900220HOCRXD07",
  "workflowEntry" : {},
  "gender" : {
    "id" : 1,
    "name" : "Male"
  },
  "taxInformation" : {},
  "createdAt" : "2017-04-01 20:21:11",
  "updatedAt" : "2017-04-01 20:21:11",
  "deletedAt" : "2017-04-04 20:21:11"
}
```

> Error Response:

```json
# Body Response
{
  "error": {
    "code": 5XXX,
    "message": "The taxpayer not found."
  }
}
```

Delete a `taxpayer` by Id.

### Service Type [`Session`](#session-service)

### Request

`DELETE /v1/taxpayers/{taxpayerId}`

Query Params |  Description 
:--------- | :-------
taxpayerId | **numeric** (required) <br> Taxpayer's Identifier.

### Response

Returns a [`TaxpayerRS`](#taxpayerrs) when all the data were sent correctly, or returns an [`error response`](#errors) if a problem happened.





## Create Tax Information ##

```shell
curl -X POST 
-H "Content-Type: application/json"
-H "x-token: 071ad636-a5c7-4fe1-aac6-60d449ccac6f" 
-d '{
  "id" : "OIPF9002203K4",
  "taxStartDate" : "2010-10-28",
  "taxLastDate" : "2014-06-26"
}' 
"https://dev.moneta.kea.mx/v1/taxpayers/5/tax-informations"

```
> Success Response:

```json
# Taxpayer Response
{
  "id" : "5",
  "userId" : "4f0f657f-0f74-4756-b86e-32facf8a35b5",
  "firstName" : "Fidel",
  "lastName" : "Ortiz Peña",
  "email" : "taxpayer@kea.mx",
  "mobile" : "0000000000",
  "birthdate" : "1990-02-20",
  "active" : true,
  "avatar" : "/img/default-avatar.jpg",
  "curp" : "OIPF900220HOCRXD07",
  "workflowEntry" : {},
  "gender" : {
    "id" : 1,
    "name" : "Male"
  },
  "taxInformation" : {
    "id" : "OIPF9002203K4",
    "taxName" : "Fidel Ortiz Peña",
    "taxStartDate" : "2010-10-28",
    "taxLastDate" : "2014-06-26",
    "taxStatus" : {},
    "taxAddress" : {},
    "taxSystems" : [],
    "createdAt" : "2017-04-01 20:21:11",
    "updatedAt" : "2017-04-01 20:21:11",
    "deletedAt" : null
  },
  "createdAt" : "2017-04-01 20:21:11",
  "updatedAt" : "2017-04-01 20:21:11",
  "deletedAt" : null
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

Create a `tax information` of taxpayer.

### Service Type [`Session`](#session-service)

### Request

`POST /v1/taxpayers/{taxpayerId}/tax-informations`

Query Params |  Description 
:--------- | :-------
taxpayerId | **numeric** (required) <br> Taxpayer's Identifier.

Property | Description
:--------- | :-----------
id | **string** (required, length=13) <br> Taxpayer identification number (RFC).
taxStartDate | **date** (optional) <br> Start date of operations.
taxLastDate | **date** (optional) <br> The last date of change status.

### Response

Returns a [`TaxpayerRS`](#taxpayerrs) when all the data were sent correctly, or returns an [`error response`](#errors) if a problem happened.





## Update Tax Information ##

```shell
curl -X PUT 
-H "Content-Type: application/json"
-H "x-token: 071ad636-a5c7-4fe1-aac6-60d449ccac6f" 
-d '{
  "id" : "OIPF9002203K4",
  "taxStartDate" : "2010-10-28",
  "taxLastDate" : "2014-06-26"
}' 
"https://dev.moneta.kea.mx/v1/taxpayers/5/tax-informations"

```
> Success Response:

```json
# Taxpayer Response
{
  "id" : "5",
  "userId" : "4f0f657f-0f74-4756-b86e-32facf8a35b5",
  "firstName" : "Fidel",
  "lastName" : "Ortiz Peña",
  "email" : "taxpayer@kea.mx",
  "mobile" : "0000000000",
  "birthdate" : "1990-02-20",
  "active" : true,
  "avatar" : "/img/default-avatar.jpg",
  "curp" : "OIPF900220HOCRXD07",
  "workflowEntry" : {},
  "gender" : {
    "id" : 1,
    "name" : "Male"
  },
  "taxInformation" : {
    "id" : "OIPF9002203K4",
    "taxName" : "Fidel Ortiz Peña",
    "taxStartDate" : "2010-10-28",
    "taxLastDate" : "2014-06-26",
    "taxStatus" : {},
    "taxAddress" : {},
    "taxSystems" : [],
    "createdAt" : "2017-04-01 20:21:11",
    "updatedAt" : "2017-04-01 20:21:11",
    "deletedAt" : null
  },
  "createdAt" : "2017-04-01 20:21:11",
  "updatedAt" : "2017-04-01 20:21:11",
  "deletedAt" : null
}
```

> Error Response:

```json
# Body Response
{
  "error": {
    "code": 5XXX,
    "message": "The tax id is invalid."
  }
}
```

Update a `tax information` of taxpayer.

### Service Type [`Session`](#session-service)

### Request

`PUT /v1/taxpayers/{taxpayerId}/tax-informations`

Query Params |  Description 
:--------- | :-------
taxpayerId | **numeric** (required) <br> Taxpayer's Identifier.

Property | Description
:--------- | :-----------
id | **string** (required, length=13) <br> Taxpayer identification number (RFC).
taxStartDate | **date** (optional) <br> Start date of operations.
taxLastDate | **date** (optional) <br> The last date of change status.

### Response

Returns a [`TaxpayerRS`](#taxpayerrs) when all the data were sent correctly, or returns an [`error response`](#errors) if a problem happened.





## Create SAT Access Key ##

```shell
curl -X POST 
-H "Content-Type: application/json"
-H "x-token: 071ad636-a5c7-4fe1-aac6-60d449ccac6f" 
-d '{
  "accessKeyType" : 1,
  "accessValue" : "odd333XD"
}' 
"https://dev.moneta.kea.mx/v1/taxpayers/5/sat-access-keys"

```
> Success Response:

```json
# Taxpayer Response
{
  "id" : "5",
  "userId" : "4f0f657f-0f74-4756-b86e-32facf8a35b5",
  "firstName" : "Fidel",
  "lastName" : "Ortiz Peña",
  "email" : "taxpayer@kea.mx",
  "mobile" : "0000000000",
  "birthdate" : "1990-02-20",
  "active" : true,
  "avatar" : "/img/default-avatar.jpg",
  "curp" : "OIPF900220HOCRXD07",
  "workflowEntry" : {},
  "gender" : {
    "id" : 1,
    "name" : "Male"
  },
  "taxInformation" : {
    "id" : "OIPF9002203K4",
    "taxName" : "Fidel Ortiz Peña",
    "taxStartDate" : "2010-10-28",
    "taxLastDate" : "2014-06-26",
    "taxStatus" : {},
    "taxAddress" : {},
    "taxSystems" : [],
    "createdAt" : "2017-04-01 20:21:11",
    "updatedAt" : "2017-04-01 20:21:11",
    "deletedAt" : null
  },
  "createdAt" : "2017-04-01 20:21:11",
  "updatedAt" : "2017-04-01 20:21:11",
  "deletedAt" : null
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

Create a taxpayer's `sat access key`.

### Service Type [`Session`](#session-service)

### Request

`POST /v1/taxpayers/{taxpayerId}/sat-access-keys`

Query Params |  Description 
:--------- | :-------
taxpayerId | **numeric** (required) <br> Taxpayer's Identifier.

Property | Description
:--------- | :-----------
[`accessKeyType`](#sat-access-key-type) | **numeric** (required) <br> Access key type.
value | **string** (required, length=8) <br> Value of access key.

### Response

Returns a [`TaxpayerRS`](#taxpayerrs) when all the data were sent correctly, or returns an [`error response`](#errors) if a problem happened.





## Read SAT Access Key ##

```shell
curl -X GET 
-H "Content-Type: application/json"
-H "x-token: 071ad636-a5c7-4fe1-aac6-60d449ccac6f"  
"https://dev.moneta.kea.mx/v1/taxpayers/5/sat-access-keys/10"

```
> Success Response:

```json
# Taxpayer SAT Access Key Response
{
  "taxpayerId" : "5",
  "key" : "Password",
  "value" : "odd333XD"
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

Read a taxpayer's `sat access key` by Id.

### Service Type [`Session`](#session-service)

### Request

`GET /v1/taxpayers/{taxpayerId}/sat-access-keys/{accessKeyId}`

Query Params |  Description 
:--------- | :-------
taxpayerId | **numeric** (required) <br> Taxpayer's Identifier.
accessKeyId | **numeric** (required) <br> SAT access key's Identifier.

### Response

Returns a [`TaxpayerSatAccessKeyRS`](#taxpayersataccesskeyrs) when all the data were sent correctly, or returns an [`error response`](#errors) if a problem happened.





## Assign a Tax System ##

```shell
curl -X POST 
-H "Content-Type: application/json"
-H "x-token: 071ad636-a5c7-4fe1-aac6-60d449ccac6f" 
-d '{
  "taxSystemId" : 1,
  "startDate" : "2015-11-23",
  "endDate" : null
}' 
"https://dev.moneta.kea.mx/v1/taxpayers/5/tax-systems"

```
> Success Response:

```json
# Taxpayer Response
{
  "id" : "5",
  "userId" : "4f0f657f-0f74-4756-b86e-32facf8a35b5",
  "firstName" : "Fidel",
  "lastName" : "Ortiz Peña",
  "email" : "taxpayer@kea.mx",
  "mobile" : "0000000000",
  "birthdate" : "1990-02-20",
  "active" : true,
  "avatar" : "/img/default-avatar.jpg",
  "curp" : "OIPF900220HOCRXD07",
  "workflowEntry" : {},
  "gender" : {
    "id" : 1,
    "name" : "Male"
  },
  "taxInformation" : {
    "id" : "OIPF9002203K4",
    "taxName" : "Fidel Ortiz Peña",
    "taxStartDate" : "2010-10-28",
    "taxLastDate" : "2014-06-26",
    "taxStatus" : {},
    "taxAddress" : {},
    "taxSystems" : [
      {
        "id" : 1,
        "name" : "Asalariados",
        "startDate" : "2015-11-23",
        "endDate" : null,
        "createdAt" : "2017-04-01 20:21:11",
        "updatedAt" : "2017-04-01 20:21:11",
        "deletedAt" : null
      }
    ],
    "createdAt" : "2017-04-01 20:21:11",
    "updatedAt" : "2017-04-01 20:21:11",
    "deletedAt" : null
  },
  "createdAt" : "2017-04-01 20:21:11",
  "updatedAt" : "2017-04-01 20:21:11",
  "deletedAt" : null
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

Assign a `tax system` to taxpayer.

### Service Type [`Session`](#session-service)

### Request

`POST /v1/taxpayers/{taxpayerId}/tax-systems`

Query Params |  Description 
:--------- | :-------
taxpayerId | **numeric** (required) <br> Taxpayer's Identifier.

Property | Description
:--------- | :-----------
[`taxSystemId`](#tax-systems) | **numeric** (required) <br> Tax system identifier.
startDate | **date** (optional) <br> Start date of system.
endDate | **date** (optional) <br> End date of system.

### Response

Returns a [`TaxpayerRS`](#taxpayerrs) when all the data were sent correctly, or returns an [`error response`](#errors) if a problem happened.





## Update a Tax System  ##

```shell
curl -X PUT 
-H "Content-Type: application/json"
-H "x-token: 071ad636-a5c7-4fe1-aac6-60d449ccac6f" 
-d '{
  "taxSystemId" : 1,
  "startDate" : "2015-11-23",
  "endDate" : "2017-11-23"
}' 
"https://dev.moneta.kea.mx/v1/taxpayers/5/tax-systems/1"

```
> Success Response:

```json
# Taxpayer Response
{
  "id" : "5",
  "userId" : "4f0f657f-0f74-4756-b86e-32facf8a35b5",
  "firstName" : "Fidel",
  "lastName" : "Ortiz Peña",
  "email" : "taxpayer@kea.mx",
  "mobile" : "0000000000",
  "birthdate" : "1990-02-20",
  "active" : true,
  "avatar" : "/img/default-avatar.jpg",
  "curp" : "OIPF900220HOCRXD07",
  "workflowEntry" : {},
  "gender" : {
    "id" : 1,
    "name" : "Male"
  },
  "taxInformation" : {
    "id" : "OIPF9002203K4",
    "taxName" : "Fidel Ortiz Peña",
    "taxStartDate" : "2010-10-28",
    "taxLastDate" : "2014-06-26",
    "taxStatus" : {},
    "taxAddress" : {},
    "taxSystems" : [
      {
        "id" : 1,
        "name" : "Asalariados",
        "startDate" : "2015-11-23",
        "endDate" : "2017-11-23",
        "createdAt" : "2017-04-01 20:21:11",
        "updatedAt" : "2017-04-01 20:21:11",
        "deletedAt" : null
      }
    ],
    "createdAt" : "2017-04-01 20:21:11",
    "updatedAt" : "2017-04-01 20:21:11",
    "deletedAt" : null
  },
  "createdAt" : "2017-04-01 20:21:11",
  "updatedAt" : "2017-04-01 20:21:11",
  "deletedAt" : null
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

Update a `tax system` of taxpayer.

### Service Type [`Session`](#session-service)

### Request

`PUT /v1/taxpayers/{taxpayerId}/tax-systems/{taxSystemId}`

Query Params |  Description 
:--------- | :-------
taxpayerId | **numeric** (required) <br> Taxpayer's Identifier.
taxSystemId | **numeric** (required) <br> Tax system's Identifier.

Property | Description
:--------- | :-----------
startDate | **date** (optional) <br> Start date of system.
endDate | **date** (optional) <br> End date of system.

### Response

Returns a [`TaxpayerRS`](#taxpayerrs) when all the data were sent correctly, or returns an [`error response`](#errors) if a problem happened.





## Remove a Tax System  ##

```shell
curl -X DELETE 
-H "Content-Type: application/json"
-H "x-token: 071ad636-a5c7-4fe1-aac6-60d449ccac6f" 
"https://dev.moneta.kea.mx/v1/taxpayers/5/tax-systems/1"

```
> Success Response:

```json
# Taxpayer Response
{
  "id" : "5",
  "userId" : "4f0f657f-0f74-4756-b86e-32facf8a35b5",
  "firstName" : "Fidel",
  "lastName" : "Ortiz Peña",
  "email" : "taxpayer@kea.mx",
  "mobile" : "0000000000",
  "birthdate" : "1990-02-20",
  "active" : true,
  "avatar" : "/img/default-avatar.jpg",
  "curp" : "OIPF900220HOCRXD07",
  "workflowEntry" : {},
  "gender" : {
    "id" : 1,
    "name" : "Male"
  },
  "taxInformation" : {
    "id" : "OIPF9002203K4",
    "taxName" : "Fidel Ortiz Peña",
    "taxStartDate" : "2010-10-28",
    "taxLastDate" : "2014-06-26",
    "taxStatus" : {},
    "taxAddress" : {},
    "taxSystems" : [],
    "createdAt" : "2017-04-01 20:21:11",
    "updatedAt" : "2017-04-01 20:21:11",
    "deletedAt" : null
  },
  "createdAt" : "2017-04-01 20:21:11",
  "updatedAt" : "2017-04-01 20:21:11",
  "deletedAt" : null
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

Remove a `tax system` of taxpayer.

### Service Type [`Session`](#session-service)

### Request

`DELETE /v1/taxpayers/{taxpayerId}/tax-systems/{taxSystemId}`

Query Params |  Description 
:--------- | :-------
taxpayerId | **numeric** (required) <br> Taxpayer's Identifier.
taxSystemId | **numeric** (required) <br> Tax system's Identifier.

### Response

Returns a [`TaxpayerRS`](#taxpayerrs) when all the data were sent correctly, or returns an [`error response`](#errors) if a problem happened.





## Create a Tax Address ##

```shell
curl -X POST 
-H "Content-Type: application/json"
-H "x-token: 071ad636-a5c7-4fe1-aac6-60d449ccac6f" 
-d '{
  "country" : "México",
  "district" : "San Simon Ticumac",
  "locality" : "Benito Juárez",
  "numExt" : "69 Dep. 401",
  "numInt" : "",
  "reference" : "",
  "state" : "Ciudad de México",
  "street" : "Canarias",
  "township" : "Benito Juárez",
  "zipCode" : "03660"
}' 
"https://dev.moneta.kea.mx/v1/taxpayers/5/tax-addresses"

```
> Success Response:

```json
# Taxpayer Response
{
  "id" : "5",
  "userId" : "4f0f657f-0f74-4756-b86e-32facf8a35b5",
  "firstName" : "Fidel",
  "lastName" : "Ortiz Peña",
  "email" : "taxpayer@kea.mx",
  "mobile" : "0000000000",
  "birthdate" : "1990-02-20",
  "active" : true,
  "avatar" : "/img/default-avatar.jpg",
  "curp" : "OIPF900220HOCRXD07",
  "workflowEntry" : {},
  "gender" : {
    "id" : 1,
    "name" : "Male"
  },
  "taxInformation" : {
    "id" : "OIPF9002203K4",
    "taxName" : "Fidel Ortiz Peña",
    "taxStartDate" : "2010-10-28",
    "taxLastDate" : "2014-06-26",
    "taxStatus" : {},
    "taxAddress" : {
      "id" : 29,
      "country" : "México",
      "district" : "San Simon Ticumac",
      "locality" : "Benito Juárez",
      "numExt" : "69 Dep. 401",
      "numInt" : "",
      "reference" : "",
      "state" : "Ciudad de México",
      "street" : "Canarias",
      "township" : "Benito Juárez",
      "zipCode" : "03660",
      "createdAt" : "2017-04-01 20:21:11",
      "updatedAt" : "2017-04-01 20:21:11",
      "deletedAt" : null
    },
    "taxSystems" : [
      {
        "id" : 1,
        "name" : "Asalariados",
        "startDate" : "2015-11-23",
        "endDate" : null,
        "createdAt" : "2017-04-01 20:21:11",
        "updatedAt" : "2017-04-01 20:21:11",
        "deletedAt" : null
      }
    ],
    "createdAt" : "2017-04-01 20:21:11",
    "updatedAt" : "2017-04-01 20:21:11",
    "deletedAt" : null
  },
  "createdAt" : "2017-04-01 20:21:11",
  "updatedAt" : "2017-04-01 20:21:11",
  "deletedAt" : null
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

Create a `tax address` to taxpayer.

### Service Type [`Session`](#session-service)

### Request

`POST /v1/taxpayers/{taxpayerId}/tax-addresses`

Query Params |  Description 
:--------- | :-------
taxpayerId | **numeric** (required) <br> Taxpayer's Identifier.

Property | Description
:--------- | :-----------
country | **string** (required, length=150) <br> Name of country.
district | **string** (optional, length=150) <br> Name of district.
locality | **string** (optional, length=150) <br> Name of locality.
numExt | **string** (required, length=20) <br> Exterior number.
numInt | **string** (optional, length=20) <br> Interior number.
reference | **string** (optional, length=300) <br> Reference of address.
state | **string** (required, length=150) <br> Name of state.
street | **string** (required, length=300) <br> Name of street.
township | **string** (optional, length=150) <br> Name of township.
zipCode | **string** (required, length=10) <br> Number of zip code.

### Response

Returns a [`TaxpayerRS`](#taxpayerrs) when all the data were sent correctly, or returns an [`error response`](#errors) if a problem happened.





## Update Tax Address ##

```shell
curl -X PUT 
-H "Content-Type: application/json"
-H "x-token: 071ad636-a5c7-4fe1-aac6-60d449ccac6f" 
-d '{
  "country" : "México",
  "district" : "San Simon Ticumac",
  "locality" : "Benito Juárez",
  "numExt" : "69",
  "numInt" : "",
  "reference" : "",
  "state" : "Ciudad de México",
  "street" : "Canarias",
  "township" : "Benito Juárez",
  "zipCode" : "03660"
}' 
"https://dev.moneta.kea.mx/v1/taxpayers/5/tax-addresses"

```
> Success Response:

```json
# Taxpayer Response
{
  "id" : "5",
  "userId" : "4f0f657f-0f74-4756-b86e-32facf8a35b5",
  "firstName" : "Fidel",
  "lastName" : "Ortiz Peña",
  "email" : "taxpayer@kea.mx",
  "mobile" : "0000000000",
  "birthdate" : "1990-02-20",
  "active" : true,
  "avatar" : "/img/default-avatar.jpg",
  "curp" : "OIPF900220HOCRXD07",
  "workflowEntry" : {},
  "gender" : {
    "id" : 1,
    "name" : "Male"
  },
  "taxInformation" : {
    "id" : "OIPF9002203K4",
    "taxName" : "Fidel Ortiz Peña",
    "taxStartDate" : "2010-10-28",
    "taxLastDate" : "2014-06-26",
    "taxStatus" : {},
    "taxAddress" : {
      "id" : 29,
      "country" : "México",
      "district" : "San Simon Ticumac",
      "locality" : "Benito Juárez",
      "numExt" : "69",
      "numInt" : "",
      "reference" : "",
      "state" : "Ciudad de México",
      "street" : "Canarias",
      "township" : "Benito Juárez",
      "zipCode" : "03660",
        "createdAt" : "2017-04-01 20:21:11",
        "updatedAt" : "2017-04-01 20:21:11",
        "deletedAt" : null
    },
    "taxSystems" : [
      {
        "id" : 1,
        "name" : "Asalariados",
        "startDate" : "2015-11-23",
        "endDate" : null,
        "createdAt" : "2017-04-01 20:21:11",
        "updatedAt" : "2017-04-01 20:21:11",
        "deletedAt" : null
      }
    ],
    "createdAt" : "2017-04-01 20:21:11",
    "updatedAt" : "2017-04-01 20:21:11",
    "deletedAt" : null
  },
  "createdAt" : "2017-04-01 20:21:11",
  "updatedAt" : "2017-04-01 20:21:11",
  "deletedAt" : null
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

Update `tax address` of taxpayer.

### Service Type [`Session`](#session-service)

### Request

`POST /v1/taxpayers/{taxpayerId}/tax-addresses/{addressId}`

Query Params |  Description 
:--------- | :-------
taxpayerId | **numeric** (required) <br> Taxpayer's Identifier.
addressId | **numeric** (required) <br> Address's Identifier.

Property | Description
:--------- | :-----------
country | **string** (required, length=150) <br> Name of country.
district | **string** (optional, length=150) <br> Name of district.
locality | **string** (optional, length=150) <br> Name of locality.
numExt | **string** (required, length=20) <br> Exterior number.
numInt | **string** (optional, length=20) <br> Interior number.
reference | **string** (optional, length=300) <br> Reference of address.
state | **string** (required, length=150) <br> Name of state.
street | **string** (required, length=300) <br> Name of street.
township | **string** (optional, length=150) <br> Name of township.
zipCode | **string** (required, length=10) <br> Number of zip code.

### Response

Returns a [`TaxpayerRS`](#taxpayerrs) when all the data were sent correctly, or returns an [`error response`](#errors) if a problem happened.





## Create Notification ##



## Read Notification ##



## Read Notifications ##



## Update Notification Status ##



## Update Notification Status ##



