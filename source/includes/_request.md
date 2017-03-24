# Request Objects

Information for objects shared in request.

## LoginClientRQ

```json
# LoginClientRQ
{
	"username" : "fxtWebSite",
	"password" : "901482"
}
```

Attribute | Required | Type  | Maxlength 
:--------- | :-------: | :-------: | :-------:
username | true | String | 150 chars
password | true | String | 150 chars

## TaxpayerRQ

Attribute | Required | Type  | Maxlength 
:--------- | :-------: | :-------: | :-------:
firstName | true | String | 150 chars
lastName | true | String | 150 chars
email | true | String | 250 chars
cellphone | true | String | 10 chars
taxpayerType | true | Int | 
authenticationType | true | Int | 

## UpdateTaxpayerRQ

Attribute | Required | Type  | Maxlength 
:--------- | :-------: | :-------: | :-------:
id | true | Int | 
firstName | true | String | 150 chars
lastName | true | String | 150 chars
cellphone | true | String | 10 chars