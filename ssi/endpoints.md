# Endpoints

## Create a local did for the wallet \(User\)

POST: /wallet/did/create \(Create a local DID\)

**Parameters:** No parameters

**Response**

![](../.gitbook/assets/5.png)

## Create a new connection invitation \(Municipality\)

POST: /connections/create-invitation \(Create a new connection invitation\)

Parameters

![](../.gitbook/assets/6.png)

Response

![](../.gitbook/assets/7.png)

## Send a schema to the ledger

POST: /schemas \(Sends a schema to the ledger\)

Parameters

![](../.gitbook/assets/8.png)

Response

![](../.gitbook/assets/9.png)

## Send a credential definition to the ledger

POST: /credential-definitions \(Sends a credential definition to the ledger\)

Parameters

![](../.gitbook/assets/10.png)

Response

![](../.gitbook/assets/11.png)

## Receive a new connection invitation\(User\)

POST: /connections/receive-invitation \(Receive a new connection invitation\)

Parameters

![](../.gitbook/assets/12.png)

Response

![](../.gitbook/assets/13.png)

## Send Issuer a credential proposal

POST: /issue-credential/send-proposal \(Send issuer a credential proposal\)

Parameters

![](../.gitbook/assets/14.png)

Response

![](../.gitbook/assets/15.png)



**Did example**

```text
{
    "result": {
    "did": "YVJfCH2gPuK3H1qTrZdm8t",
    "verkey": "JAQ5tQnaEoroWesuvmbD4euji6pC6dq8vbw29RTSs45P",
    "posture": "wallet_only" }
}
```

**Schema example**

```text
{
    "schema_id": "V4SGRU86Z58d6TV7PBUe6f:2:identification:1.0",
    "schema": {
        "ver": "1.0",
        “id”: "V4SGRU86Z58d6TV7PBUe6f:2:identification:1.0",
        “name": "identification”,
        “version": "1.0”,
        “attrNames”: [
        “name”,
        “surname”,
        “fathersname”,
        “mothersname”,
        “motherssurname”,
        “dateofbirth”,
        “placeofbirth”,
        “registeredcitizen”
    ],
    "seqNo": 9
    }
}
```

