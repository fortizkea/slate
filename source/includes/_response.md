# Response Objects

Information for objects shared in response.





## ConnectionRS ##

Attribute | Description
:--------- | :-------
token | **string** <br> Token's Universally unique identifier.
createdAt | **datetime** <br> The date and time of token's create.
updatedAt | **datetime** <br> The date and time of token's update.
expiresIn | **numeric** <br> The lifetime of the connection token in seconds.





## SessionRS

Attribute | Description
:--------- | :-------
token |  **string** <br> Token's Universally unique identifier.
createdAt | **datetime** <br> The date and time of token's create.
updatedAt | **datetime** <br> The date and time of token's update.
expiresIn | **numeric** <br> The lifetime of the session token in seconds.
userId | **string** <br> The user's universally unique identifier.





## TransactionRS ##

Attribute | Description
:--------- | :-------
token | **string** <br> Token's Universally unique identifier.
createdAt | **datetime** <br> The date and time of token's create.
updatedAt | **datetime** <br> The date and time of token's update.
expiresIn | **numeric** <br> The lifetime of the transaction token in seconds.
userId | **string** <br> The user's universally unique identifier.





## ResetPasswordRS ##

Attribute | Description
:--------- | :-------
token | **string** <br> Token's Universally unique identifier.
createdAt | **datetime** <br> The date and time of token's create.
updatedAt | **datetime** <br> The date and time of token's update.
userId | **string** <br> The user's universally unique identifier.





## TransactionResetPasswordRS ##

Attribute | Description
:--------- | :-------
transactionToken | **string** <br> Transaction's Universally unique identifier.
createdAt | **datetime** <br> The date and time of token's create.
updatedAt | **datetime** <br> The date and time of token's update.
userId | **string** <br> The user's universally unique identifier.





## ErrorRS

Attribute | Description
:--------- | :-------
code | **numeric** <br> The error code.
message | **string** <br> The error message.





## TaxpayerRS

Property | Description 
:--------- | :-------
id | **numeric** <br> Identifier of taxpayer.
firstName | **string** <br> First name of profile.
lastName | **string** <br> Last name of profile.
email | **string** <br> Email of profile.
mobile | **string** <br> Mobile number of profile.
birthdate | **date** <br> Birthdate of profile.
userId | **string** <br> User universally unique identifier.
active | **boolean** <br> If the user is active the value is true anotherwise is false.
avatar | **string** <br> Url of image profile.
curp | **string** <br> Unique population registry code of profile.
[workflowEntry](#workflowentryrs) | **object** <br> Workflow entry of taxpayer.
[gender](#genderrs) | **object** <br> Gender of profile.
[taxInformation](#taxinformationrs) | **object** <br> Tax information of profile.
createdAt | **datetime** <br> Date and time of created.
updatedAt | **datetime** <br> Date and time of updated.
deletedAt | **datetime** <br> Date and time of deleted.





## TaxInformationRS

Property | Description 
:--------- | :-------
id | **string** <br> Identifier of tax information.
taxName | **string** <br> Business name.
taxStartDate | **date** <br> Start date of operations.
taxLastDate | **date** <br> The last date of change status.
[taxStatus](#taxstatusrs) | **object** <br> Tax status of register.
[taxAddress](#addressrs) | **object** <br> Tax address.
[taxSystems](#taxsystemrs) | **array** <br> Array of tax systems.
createdAt | **datetime** <br> Date and time of created.
updatedAt | **datetime** <br> Date and time of updated.
deletedAt | **datetime** <br> Date and time of deleted.





## TaxStatusRS

Property | Description 
:--------- | :-------
id | **numeric** <br> Identifier of status.
name | **string** <br> Name of status.





## AddressRS
Property | Description 
:--------- | :-------
id | **numeric** <br> Identifier of address.
country | **string** <br> Name of country.
district | **string** <br> Name of district.
locality | **string** <br> Name of locality.
numExt | **string** <br> Exterior number.
numInt | **string** <br> Interior number.
reference | **string** <br> Reference of address.
state | **string** <br> Name of state.
street | **string** <br> Name of street.
township | **string** <br> Name of township.
zipCode | **string** <br> Number of zip code.
createdAt | **datetime** <br> Date and time of created.
updatedAt | **datetime** <br> Date and time of updated.
deletedAt | **datetime** <br> Date and time of deleted.


	


## TaxSystemRS

Property | Description 
:--------- | :-------
id | **numeric** <br> Identifier of tax system.
name | **string** <br> Name of tax system.
startDate | **date** <br> Start date of system.
endDate | **date** <br> End date of system.
createdAt | **datetime** <br> Date and time of created.
updatedAt | **datetime** <br> Date and time of updated.
deletedAt | **datetime** <br> Date and time of deleted.




## GenderRS

Property | Description 
:--------- | :-------
id | **numeric** <br> Identifier of gender.
name | **string** <br> Name of gender.





## TaxpayerSatAccessKeyRS

Property | Description 
:--------- | :-------
taxpayerId | **numeric** <br> Identifier of taxpayer.
key | **string** <br> Key type of access.
value | **string** <br> Value of access.





## WorkflowEntryRS

Property | Description 
:--------- | :-------
id | **numeric** <br> Identifier of entry.
[workflowStep](#workflowsteprs) | **object** <br> Workflow step object.
[workflow](#workflowrs) | **object** <br> Workflow object.
createdAt | **datetime** <br> Date and time of created workflow entry.
updatedAt | **datetime** <br> Date and time of updated workflow entry.





## WorkflowStepRS

Property | Description 
:--------- | :-------
id | **string** <br> Identifier of workflow step.
name | **string** <br> Name of the workflow step.
[workflowStatus](#workflowstatusrs) | **object** <br> Status of workflow.





## WorkflowRS

Property | Description 
:--------- | :-------
id | **numeric** <br> Identifier of workflow.
name | **string** <br> Name of workflow.





## WorkflowStatusRS

Property | Description 
:--------- | :-------
id | **numeric** <br> Identifier of status.
name | **string** <br> Name of status.


