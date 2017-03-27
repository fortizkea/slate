# Taxpayers





## Create Taxpayer ##

```shell
curl -X POST -H "x-token: 071ad636-a5c7-4fe1-aac6-60d449ccac6f" -H "Content-Type: application/json" -H "Cache-Control: no-cache" -d '{
	"firstName" : "taxpayerFirstName",
	"lastName" : "taxpayerLastName",
	"email" : "taxpayer@kea.mx",
	"cellphone" : "0000000000",
	"taxpayerType" : "1"
}' "https://{ApiURL}/v1/taxpayers"

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

Update a `taxpayer` by Id.

### Service Type [`Session`](#session-service)

### Request

`PUT /v1/taxpayers/{taxpayerId}`

Property | Description
:--------- | :-----------
userId | **string** (required, length=36) <br> User universally unique identifier.
firstName | **string** (required, length=50) <br> First name of profile.
lastName | **string** (required, length=50) <br> Last name of profile.
mobile | **string** (required, length=16) <br> Mobile number of profile.
birthdate | **date** (optional) <br> Birthdate of profile.
curp | **string** (optional, length=18) <br> Unique population registry code of profile.

### Response

Returns a [`TaxpayerRS`](#taxpayerrs) when all the data were sent correctly, or returns an [`error response`](#errors) if a problem happened.





## Delete Taxpayer ##

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



