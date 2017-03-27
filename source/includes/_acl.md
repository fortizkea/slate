# Access Control

Capa de abstracción responsable de la autorización de ejecución de servicios que pueden ejecutar los clientes o usuarios con credenciales válidas.

Se considera **Cliente** aquellas plataformas que desean consumir los servicios; por ejemplo el WebSite, la Aplicación Movil (Android ó iOS).

Se considera **Usuario** a la personas con un correo válido y una contraseña que utiliza los servicios expuestos por un sitio web ó aplicación movil; por ejemplo los contribuyentes, contadores y administradores de FIXAT. 

## Connection Service ##
Servicios donde su caracteristica principal es exponer información publica; por ejemplo Catálogos de Productos, Estados, entre otros.

### How to get ConnecctionToken
Para obtener un token de tipo **`ConnectionToken`** se debe realizar la autenticación del cliente a través del siguiente servicio [`Login Client`](#login-client).

### Header Request Service

```shell
  curl -X GET 
  -H "Content-Type: application/json" 
  -H "x-token: a0294e07-ea36-4cc6-9295-f866c9e40851"
  "https://dev.moneta.kea.mx/v1/auth/logout-client"
```

Cuando se consumen un servicio de tipo **`ConnectionService`**, es requerido enviar en la cabecera Http lo siguiente:

HTTP Header | Required | Type | Description
:--------- | :---------: | :---------: | :-----------
x-token | true | String | Universally unique identifier.

### Header Response Service

```text
# Status
Status: {exception.code}

# Header Response
x-created-at: Mon, 20 Mar 2017 19:53:21 GMT
x-token: 4f0f657f-0f74-4756-b86e-32facf8a35b5
x-updated-at: Mon, 20 Mar 2017 19:53:21 GMT
```

En el momento que se recibe la respuesta del servicio; en la cabecera http se recibe lo siguiente:

HTTP Header | Type | Description
:--------- | :---------: | :-----------
x-token | String | Universally unique identifier.
x-created-at | Datetime | Datetime of creation token.
x-updated-at | Datetime | Datetime of update token.
x-time-to-live | Numeric | Time to live of token (seconds format).

## Session Service ##

Servicios donde su caracteristica principal es exponer información privada; por ejemplo Consultar la información del contribuyente, del contador, entre otros.

### How to get SessionToken
Para obtener un token de tipo **`SessionToken`** se debe realizar la autenticación del usuario a través de los siguientes servicios:

* Si deseas crear la sesión de un contribuyente se debe realizar la autenticación a través del siguiente servicio [`Login Taxpayer`](#login-taxpayer).

* Si deseas crear la sesión de un contador se debe realizar la autenticación a través del siguiente servicio [`Login Accountant`](#login-accountant).

* Si deseas crear la sesión de un operador de FIXAT se debe realizar la autenticación a través del siguiente servicio [`Login Manager`](#login-manager).

### Header Request Service

```shell
  curl -X GET 
  -H "Content-Type: application/json" 
  -H "x-token: a0294e07-ea36-4cc6-9295-f866c9e40851"
  "https://dev.moneta.kea.mx/v1/auth/login-taxpayer"
```

Cuando se consume un servicio de tipo **`SessionService`**, es requerido enviar en la cabecera Http lo siguiente:

HTTP Header | Required | Type | Description
:--------- | :---------: | :---------: | :-----------
x-token | true | String | Universally unique identifier.

### Header Response Service

```text
# Status
Status: {exception.code}

# Header Response
x-created-at: Mon, 20 Mar 2017 19:53:21 GMT
x-token: 4f0f657f-0f74-4756-b86e-32facf8a35b5
x-updated-at: Mon, 20 Mar 2017 19:53:21 GMT
```

En el momento que se recibe la respuesta del servicio; en la cabecera http se recibe lo siguiente:

HTTP Header | Type | Description
:--------- | :---------: | :-----------
x-token | String | Universally unique identifier.
x-created-at | Datetime | Datetime of creation token.
x-updated-at | Datetime | Datetime of update token.
x-time-to-live | Numeric | Time to live of token (seconds format).

## Transaction Service ##

Servicios donde su caracteristica principal es ejecutar un conjunto de procesos que se garantiza que su operación es satisfactoria; de recibir un error dicha transacción se cancela; por ejemplo pago de servicios, entre otros.

### How to get TransactionToken
Para obtener un token de tipo **`TransactionToken`** se debe crear a través del siguiente servicio [`Begin Transaction`](#begin-transaction).

### Header Request Service

```shell
  curl -X GET 
  -H "Content-Type: application/json" 
  -H "x-token: a0294e07-ea36-4cc6-9295-f866c9e40851"
  "https://dev.moneta.kea.mx/v1/auth/logout-client"
```

Cuando se requiere consumir los servicios de tipo **`TransactionService`**, es requerido enviar en la cabecera Http lo siguiente:

HTTP Header | Required | Type | Description
:--------- | :---------: | :---------: | :-----------
x-token | true | String | Universally unique identifier.

### Header Response Service

```text
# Status
Status: {exception.code}

# Header Response
x-created-at: Mon, 20 Mar 2017 19:53:21 GMT
x-token: 4f0f657f-0f74-4756-b86e-32facf8a35b5
x-updated-at: Mon, 20 Mar 2017 19:53:21 GMT
```

En el momento que se recibe la respuesta del servicio; en la cabecera http se recibe lo siguiente:

HTTP Header | Type | Description
:--------- | :---------: | :-----------
x-token | String | Universally unique identifier.
x-created-at | Datetime | Datetime of creation token.
x-updated-at | Datetime | Datetime of update token.
x-time-to-live | Numeric | Time to live of token (seconds format).