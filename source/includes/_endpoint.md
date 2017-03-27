#API Endpoint

```sell

# Authentication Login
/v1/auth/login/client
/v1/auth/login/taxpayer
/v1/auth/login/accountant
/v1/auth/login/manager

# Authentication Logout
/v1/auth/logout/client
/v1/auth/logout/taxpayer
/v1/auth/logout/accountant
/v1/auth/logout/manager

# Authentication Reset Password
/v1/auth/reset-password

# Transaction Token
/v1/auth/begin-transaction
/v1/auth/end-transaction

# Validate Token
/v1/auth/validate/connection
/v1/auth/validate/session
/v1/auth/validate/transaction

# Taxpayers
/v1/taxpayers
/v1/taxpayers/{taxpayerId}
/v1/taxpayers/{taxpayerId}/tax-informations
/v1/taxpayers/{taxpayerId}/tax-systems
/v1/taxpayers/{taxpayerId}/tax-systems/{taxSystemId}
/v1/taxpayers/{taxpayerId}/tax-addresses
/v1/taxpayers/{taxpayerId}/tax-addresses/{taxAddressId}
/v1/taxpayers/{taxpayerId}/sat-access-keys
/v1/taxpayers/{taxpayerId}/sat-access-keys/{satAccessKeyId}
/v1/taxpayers/{taxpayerId}/notifications
/v1/taxpayers/{taxpayerId}/notifications/{notificationId}

# Accountants
/v1/accountants
/v1/accountants/{accountantId}

# Managers
/v1/managers
/v1/managers/{managerId}


```

The Moneta REST API has a test environment and a production environment.

### **Development Enviroment:** 
`https://dev.moneta.kea.mx`

### **Production Enviroment:** 
`https://moneta.kea.mx`