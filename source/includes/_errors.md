# Errors

## Http Errors

Error Code | Meaning
:----------: | :-------
400 | Bad Request -- Your request sucks
401 | Unauthorized -- Your API key is wrong
403 | Forbidden -- The kitten requested is hidden for administrators only
404 | Not Found -- The specified kitten could not be found
405 | Method Not Allowed -- You tried to access a kitten with an invalid method
406 | Not Acceptable -- You requested a format that isn't json
410 | Gone -- The kitten requested has been removed from our servers
418 | I'm a teapot
429 | Too Many Requests -- You're requesting too many kittens! Slow down!
500 | Internal Server Error -- We had a problem with our server. Try again later.
503 | Service Unavailable -- We're temporarily offline for maintenance. Please try again later.

## Access Control Errors

Error Code | Meaning
:----------: | :-------
0000 | InvalidClientCredentialsException --  The client credentials are invalid.
0000 | MaxClientConnectionException -- Too many client connections..
0000 | InvalidClientConnectionException -- The client information is invalid.
0000 | InvalidClientConnectionException --  The client information is invalid.

## Taxpayer Errors

Error Code | Meaning
:----------: | :-------
0000 | EmailExistException --  The email {emailValue} already exist.
0000 | InvalidEmailException -- The {emailName} is invalid email address.
0000 | IvalidCellphoneException -- The {phoneNumber} is invalid only allow digits.
0000 | InvalidParamException --  The param {paramName} is invalid.
0000 | TaxpayerTypeNotExistsException --  The taxpayer type {taxpayerTypeValue} not exists.
0000 | RequiredParamException -- The param {paramName} is required.
0000 | MaxlengthParamException -- The maximun length of {paramName} is {maxlengthValue}.
0000 | TaxpayerNotFoundException --  The taxpayer not found.
0000 | InvalidTaxIdException --  The tax id {taxId} is invalid.
0000 | InvalidKeyAccessSatException --  The key access sat {taxId} is invalid.
0000 | DeleteTaxpayerException --  The taxpayer was not deleted.



