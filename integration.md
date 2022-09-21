<h1 style="text-align: center;"> Trueqqe Integration Api </h1>

With the Trueqqe API, you can easily and quickly integrate. These 
documents will cover the available endpoints and provide sample code for 
using the API.

If you have any questions, please email us at api@trueqqe.com.

<br>

<h1> 🔒 Security </h1>

Security in Trueqqe API is very important for a successful integration. To 
access the Trueqqe API, it is essential that all requests have the 
following headers.

```json
{
    "Authorization": "Bearer ${token}",
    "Secret-key": 
"$2a$12$TIo4wg9EgX7v.ZCAYQmF9exR5a/XHwilrq0fUC9evLUEo9JWC6tLC",
    "Public-key": "-----PUB_KEY-----"
}
```

  > If you are interested in performing a correct integration, you should 
send an email to api@trueqqe.com to provide you information and necessary 
header values


<br>

<h1> 💵 Banking transactions </h1>

## 💸 **Cash-out**

<details>
<summary style="font-size: 1.1em; color: #45B39D">Notify a 
withdrawal</summary>

> Request

```json
{
    "method": "PUT",
    "url": "/api/account-management/cash-out",
    "headers": {
        "Authorization": "Bearer ${token}",
        "Secret-key": 
"$2a$12$TIo4wg9EgX7v.ZCAYQmF9exR5a/XHwilrq0fUC9evLUEo9JWC6tLC",
        "Public-key": "-----PUB_KEY-----"
    },
    "payload": {
        "accountNumber": "string",
        "date": "date",
        "type": "ATM" | "DIRECT_WITHDRAW",
        "ammount": number,
        "location": "string"
    }
}
```

> Description

```yml
- accountNumber: Account number that made the withdrawal
- date: Date that made the withdrawal
- type: Type of withdrawal
- ammount: Ammount of united states dollars
- location: Origin bank location
```

> Response

```json
{
    "status": "string",
}
```
</details>

<br>

## 💰 **Cash-in**

<details>
<summary style="font-size: 1.1em; color: #45B39D">Notify a 
deposit</summary>

> Request

```json
{
    "method": "POST",
    "url": "/api/account-management/cash-in",
    "headers": {
        "Authorization": "Bearer ${token}",
        "Secret-key": 
"$2a$12$TIo4wg9EgX7v.ZCAYQmF9exR5a/XHwilrq0fUC9evLUEo9JWC6tLC",
        "Public-key": "-----PUB_KEY-----"
    },
    "payload": {
        "accountNumber": "string",
        "date": "date",
        "type": "ATM" | "DIRECT_DEPOSIT",
        "ammount": number,
        "location": "string"
    }
}
```

> Description

```yml
- accountNumber: Account number that made the deposit
- date: Date that made the deposit
- type: Type of deposit
- ammount: Ammount of united states dollars
- location: Origin bank location
```

> Response

```json
{
    "status": "string",
}
```
</details>

<br>

## 📟 **Compensation Package**

<details>
<summary style="font-size: 1.1em; color: #45B39D">Notify a new 
compensation package</summary>

> Request

```json
{
    "method": "POST",
    "url": "/api/account-management/cash-in",
    "headers": {
        "Authorization": "Bearer ${token}",
        "Secret-key": 
"$2a$12$TIo4wg9EgX7v.ZCAYQmF9exR5a/XHwilrq0fUC9evLUEo9JWC6tLC",
        "Public-key": "-----PUB_KEY-----"
    },
    "payload": {
        "fromAccountNumber": "string",
        "toAccountNumber": "string",
        "toAccountHolder": "string",
        "toAccountBankBranchName": "string",
        "toAccountIdentify": "string",
        "toAccountEmail": "string",
        "toAccountDescription": "string",
        "date": "date",
        "type": "NAT" | "INTL",
        "ammount": number,
        "location": "string"
    }
}
```

> Description

```yml
- fromAccountNumber: Account number that generated a line of credit 
- toAccountNumber: Account number where the payment of a line of credit 
should be made
- toAccountHolder: Destination account owner name
- toAccountBankBranchName: Destination account bank name
- toAccountIdentify: Destination account owner identify ID/CED/PASSPORT
- toAccountEmail: Destination account owner email
- toAccountDescription: Description of transaction
- date: Date that generated a line of credit 
- type: National (NAT) or international (INTL)compensation package
- ammount: Ammount of united states dollars
- location: Destination bank account
```

> Response

```json
{
    "status": "string",
}
```
</details>

<br>

<h1> 💳 Card Operations</h1>

<details>
<summary style="font-size: 1.1em; color: #45B39D">Notify Block 
Card</summary>

> Request

```json
{
    "method": "",
    "url": "/api/card-operations/block-card",
    "headers": {
        "Authorization": "Bearer ${token}",
        "Secret-key": 
"$2a$12$TIo4wg9EgX7v.ZCAYQmF9exR5a/XHwilrq0fUC9evLUEo9JWC6tLC",
        "Public-key": "-----PUB_KEY-----"
    },
    "payload": {
         "accountNumber": "string",
         "date": "date",
         "type": "PARTIAL" | "TEMPORAL" | "PERMANENT",
    }
}
```

> Description

```yml
- accountNumber: Account number that is blocked
- date: Date that is blocked
- type: Type of blocked
```

> Response

```json
{
    "status": "string",
}
```
</details>

<details>
<summary style="font-size: 1.1em; color: #45B39D">Notify Unlock 
Card</summary>

> Request

```json
{
    "method": "",
    "url": "/api/card-operations/unlock-card",
    "headers": {
        "Authorization": "Bearer ${token}",
        "Secret-key": 
"$2a$12$TIo4wg9EgX7v.ZCAYQmF9exR5a/XHwilrq0fUC9evLUEo9JWC6tLC",
        "Public-key": "-----PUB_KEY-----"
    },
    "payload": {
        "accountNumber": "string",
        "date": "date",
    }
}
```

> Description

```yml
- accountNumber: Account number that is unlock
- date: Date of unlock
```

> Response

```json
{
    "status": "string",
}
```
</details>
