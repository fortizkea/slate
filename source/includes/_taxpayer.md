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

### Service Type `ConnectionService`
Read the [`ConnectionService`](#connectionservice) requierements.

### Request

`POST /v1/taxpayers`

Send in the body params the [`TaxpayerRQ`](#taxpayerrq) object.

### Response

The service response the [`Response`](#response) object.

## Read Taxpayer By Id ##

Get a `taxpayer` by Id.

### Service Type `SessionService`
Read the [`SessionService`](#sessionservice) requierements.

### Request

`GET /v1/taxpayers/{taxpayerId}`

Query Params | Required | Type  | Description 
:--------- | :---------: | :-------: | :-------
taxpayerId | true | Int |  Taxpayer's Identifier

### Response

The service response the [`TaxpayerRS`](#taxpayerrs) object.


## Update Taxpayer ##

Update a `taxpayer` by Id.

### Service Type `SessionService`
Read the [`SessionService`](#sessionservice) requierements.

### Request

`PUT /v1/taxpayers/{taxpayerId}`

Send in the body params the [`UpdateTaxpayerRQ`](#updatetaxpayerrq) object.

### Response

The service response the [`TaxpayerRS`](#taxpayerrs) object.

## Create Tax Information ##

Create a `taxpayer's tax id`.

### Service Type `SessionService`
Read the [`SessionService`](#sessionservice) requierements.

### Request

`POST /v1/taxpayers/{taxpayerId}/tax-informations`

Send in the body params the [`TaxpayerTaxIdRQ`](#taxpayertaxidrq) object.

### Response

The service response the [`TaxpayerRS`](#taxpayerrs) object.

## Create SAT Access Key ##

Create a `taxpayer's key sat access`.

### Service Type `SessionService`
Read the [`SessionService`](#sessionservice) requierements.

### Request

`POST /v1/taxpayers/{taxpayerId}/sat-access-keys`

Send in the body params the [`KeyAccessSatTaxpayerRQ`](#keyaccesssattaxpayerrq) object.

### Response

The service response the [`TaxpayerRS`](#taxpayerrs) object.

## Delete Taxpayer ##

Delete a `taxpayer` by Id.

### Service Type `SessionService`
Read the [`SessionService`](#sessionservice) requierements.

### Request

`DELETE /v1/taxpayers/{taxpayerId}`

Query Params | Required | Type  | Description 
:--------- | :---------: | :-------: | :-------
taxpayerId | true | Int |  Taxpayer's Identifier

### Response

The service response the [`Response`](#response) object.

## Create TaxSystem ##



## Update TaxSystem ##




## Create TaxAddress ##




## Update TaxAddress ##



## Create Notification ##



## Read Notification By Id ##



## Read Notifications ##



## Update Notification Status ##



## Update Notification Status ##



