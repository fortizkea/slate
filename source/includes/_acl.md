# Access Control

The access control layer, authorize that clients and users execute services.

The **Client** is an user with valid credential to execute services; for example: website and Apps mobile (Android or iOS).

The **User** is a person with valid email and password authorize to execute services on website and Moneta REST API; for example Taxpayers, Accountants and Moneta Managers.

## Connection Service ##
The response of connection services are the public information, like countries catalogs.

### How to get Connecction Token
If your has a Client's valid credentials, execute [`Login Client`](#login-client) service.

### Header Request Service

```shell
  curl -X GET 
  -H "Content-Type: application/json" 
  -H "x-token: a0294e07-ea36-4cc6-9295-f866c9e40851"
  "https://dev.moneta.kea.mx/v1/auth/logout-client"
```
When you want to execute the **`connection`** service type, is required add the next HTTP headers:

HTTP Header | Description
:--------- | :-----------
x-token | **string** (required, length=36) <br> Universally unique identifier.

### Header Response Service

```text
# Header Response
x-token: 4f0f657f-0f74-4756-b86e-32facf8a35b5
x-created-at: 2017-04-02 21:32:33
x-updated-at: 2017-04-02 21:32:33
x-time-to-live: 86400
```
The services response the next HTTP Headers:

HTTP Header | Description
:--------- | :-----------
x-token | **string** <br> Universally unique identifier.
x-created-at | **datetime** <br> Datetime of creation token.
x-updated-at | **datetime** <br> Datetime of update token.
x-time-to-live | **numeric** <br> Time to live of token (seconds format).

## Session Service ##

The response of connection services are the private information, like taxpayer data or accountant profile.

### How to get Session Token
If you want begin the session on the platform is required a user's valid credentials.

* If you has a taxpayer's credentials, execute the [`Login Taxpayer`](#login-taxpayer) service.

* If you has a accountant's credentials, execute the [`Login Accountant`](#login-accountant) service.

* If you has a moneta manager's credentials, execute the [`Login Manager`](#login-manager) service.

### Header Request Service

```shell
  curl -X GET 
  -H "Content-Type: application/json" 
  -H "x-token: a0294e07-ea36-4cc6-9295-f866c9e40851"
  "https://dev.moneta.kea.mx/v1/auth/login-taxpayer"
```

When you want to execute the **`session`** service type, is required add the next HTTP headers:

HTTP Header | Description
:--------- | :-----------
x-token | **string** (required, length=36) <br> Universally unique identifier.

### Header Response Service

```text
# Header Response
x-token: 4f0f657f-0f74-4756-b86e-32facf8a35b5
x-created-at: 2017-04-02 21:32:33
x-updated-at: 2017-04-02 21:32:33
x-time-to-live: 86400
```

The services response the next HTTP Headers:

HTTP Header | Description
:--------- | :-----------
x-token | **string** <br> Universally unique identifier.
x-created-at | **datetime** <br> Datetime of creation token.
x-updated-at | **datetime** <br> Datetime of update token.
x-time-to-live | **numeric** <br> Time to live of token (seconds format).

## Transaction Service ##

Transaction service is the process of completing a task and/or user request either instantly or at runtime. It is the collection of different interrelated tasks and processes that must work in sync to finish an overall business process transaction. for example when your payment a Moneta Product.

### How to get Transaction Token
When you need to execute transaction services is requiered follow the next steps:

1 If your has a user's session then execute [`Begin Transaction`](#begin-transaction) service.

2 Execute transaction service type.

3 When you want finished the transaction then execute [`End Transaction`](#end-transaction) service.

### Header Request Service

```shell
  curl -X POST 
  -H "Content-Type: application/json" 
  -H "x-token: a0294e07-ea36-4cc6-9295-f866c9e40851"
  "https://dev.moneta.kea.mx/v1/auth/begin-transaction"
```

When you want to execute the **`transaction`** service type, is required add the next HTTP headers:

HTTP Header | Description
:--------- | :-----------
x-token | **string** (required, length=36) <br> Universally unique identifier.

### Header Response Service

```text
# Header Response
x-token: 4f0f657f-0f74-4756-b86e-32facf8a35b5
x-created-at: 2017-04-02 21:32:33
x-updated-at: 2017-04-02 21:32:33
x-time-to-live: 86400
```

The services response the next HTTP Headers:

HTTP Header | Description
:--------- | :-----------
x-token | **string** <br> Universally unique identifier.
x-created-at | **datetime** <br> Datetime of creation token.
x-updated-at | **datetime** <br> Datetime of update token.
x-time-to-live | **numeric** <br> Time to live of token (seconds format).