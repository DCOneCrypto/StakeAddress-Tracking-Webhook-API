# Wallets tracking notify (Announcement of webhook activity payment stake address)

* Readmore: https://docs.dconecrypto.finance/notify/webhooks
> Note: Create an account before using the APIs 
1. Create an account: `Mainnet` https://dconecrypto.finance
2. Create an account: `Testnet` https://testnet.dconecrypto.finance

# REST API

Network: `Mainnet`
Endpoint: `https://dconecrypto-mainnet.dconecrypto.finance/`

Network: `Testnet`
Endpoint: `https://dconecrypto-testnet.dconecrypto.finance/`


# Credentials when using API

```shell
Authorization: Bearer {{accessToken}}
```

# Authenticate
* Required field: userNameOrEmailAddress , password

```shell
curl --location 'https://dconecrypto-testnet.dconecrypto.finance/api/TokenAuth/Authenticate' \
--header 'Content-Type: application/json' \
--data '{
  "userNameOrEmailAddress": "dconecryptofinance",
  "password": "",
  "rememberClient": true
}'
```
#Example api Authenticate responses
```shell
{
  "accessToken": "string",
  "encryptedAccessToken": "string",
  "expireInSeconds": 0,
  "shouldResetPassword": true,
  "passwordResetCode": "string",
  "userId": 0,
  "requiresTwoFactorVerification": true,
  "twoFactorAuthProviders": [
    "string"
  ],
  "twoFactorRememberClientToken": "string",
  "returnUrl": "string",
  "refreshToken": "string",
  "refreshTokenExpireInSeconds": 0
}
```

# Create a new webhook (CreateOrEdit)

Once a payment is detected in the stake address, it will be activated and the webhook call will work

Example api request:
```shell
curl --location -g '{{domain}}/api/services/app/DC_WebhookWallets/CreateOrEdit' \
--header 'Authorization: Bearer {{accessToken}}' \
--header 'Content-Type: application/json' \
--data '{
    "webhookname": "",
    "webhookDescription": "",
    "webhookUrl": "https://webhook.site/9ad3f909-93b1-42da-918d-19a33445b3f2",
    "webhookStakeAddress": "stakexxxxxxxxxxxxx",
    "webhookStatus": true,
    "userId": 0,
    "id": ""
}'
```

# List of webhook connections (GetAll)

Get a list of all webhooks connected to the system

Example api request:
```shell
curl --location -g '{{domain}}/api/services/app/DC_WebhookWallets/GetAll' \
--header 'Authorization: Bearer {{accessToken}}' \
--data ''
```

# Get detailed information of a webhook (GetDC_WebhookWalletForEdit)

Get a list of all webhooks connected to the system

Example api request:
```shell
curl --location -g '{{domain}}/api/services/app/DC_WebhookWallets/GetDC_WebhookWalletForEdit?Id=d205f25a-72b6-4e0e-c9c8-08db1614d234' \
--header 'Authorization: Bearer {{accessToken}}' \
--data ''
```

# Remove webhooks (Delete)

Remove 1 webhook information and don't trigger notification when stake address payment

Example api request:
```shell
curl --location -g '{{domain}}/api/services/app/DC_WebhookWallets/Delete?null=d205f25a-72b6-4e0e-c9c8-08db1614d234' \
--header 'Authorization: Bearer {{accessToken}}' \
--data ''
```

# Get userId by token (GetAllUserForTableDropdown)

Get the userId variable and put in the userId input parameter in the "CreateOrEdit" api

```shell
curl --location -g '{{domain}}/api/services/app/DC_WebhookWallets/GetAllUserForTableDropdown' \
--header 'Authorization: Bearer {{accessToken}}' \
--data ''
```



