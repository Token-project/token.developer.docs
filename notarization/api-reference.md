# API reference

{% api-method method="post" host="https://api.ledgerproject.eu" path="/notarization/stamp" %}
{% api-method-summary %}
Stamp
{% endapi-method-summary %}

{% api-method-description %}
Creates a timestamp for a given SHA-256 hash hexadecimal digest.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Content-Type" type="string" required=false %}
application/x-www-form-urlencoded
{% endapi-method-parameter %}

{% api-method-parameter name="Authorization" type="string" required=true %}
Bearer: $TOKEN
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-body-parameters %}
{% api-method-parameter name="hash" type="string" required=true %}
SHA-256 hash
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```text
{
    "transactionId": "1b9e6cb48098bc1fd8d8bd44c53e92c394c06a41ed50ab5845ed3e8b36e9f012"
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

```text
curl -L -X POST 'https://api.token-project.eu:443/notarization/stamp' \
-H 'Content-Type: application/x-www-form-urlencoded' \
-H 'Authorization: Bearer $TOKEN' \
--data-urlencode 'hash=$HASH'
```



{% api-method method="get" host="https://api.ledgerproject.eu" path="/notarization/stamp" %}
{% api-method-summary %}
Stamp
{% endapi-method-summary %}

{% api-method-description %}
Retrieves all receipts \(also known as proofs\) for a certain stamp
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Content-Type" type="string" required=false %}
application/x-www-form-urlencoded
{% endapi-method-parameter %}

{% api-method-parameter name="Authorization" type="string" required=true %}
Bearer: $TOKEN
{% endapi-method-parameter %}
{% endapi-method-headers %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```text
[
    {
        "docType": "stamp",
        "hash": "2f3f3a85340bde09b505b0d37235d1d32a674e43a66229f9a205e7d8d5328ed1"
    }
]
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

```text
curl -L -X GET 'https://api.token-project.eu:443/notarization/stamp/$STAMP' \
-H 'Content-Type: application/x-www-form-urlencoded' \
-H 'Authorization: Bearer $TOKEN' \
--data-urlencode 'hash=$HASH'
```

⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: Retrieving receipts for a stamp

### Description: Retrieves all receipts \(also known as proofs in former Stampery API versions\) for a certain stamp.

The response is a JSON-encoded object containing an array of stamps. If a certain receipt found inside a stamp is a number instead of an object, that number is the estimated number of seconds before the final receipt will be ready. Method: GET

> ```text
> {{protocol}}://{{host}}:{{port}}/{{services.notarization}}/stamp/2f3f3a85340bde09b505b0d37235d1d32a674e43a66229f9a205e7d8d5328ed1
> ```
>
> ### Headers

| Content-Type | Value |
| :--- | :--- |
| Content-Type | application/x-www-form-urlencoded |

⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃



## End-point: SignUp

### Description: Creates a timestamp for a given SHA-256 hash hexadecimal digest. Please note that POST requests must include the Content-Type: application/json header.

The response is JSON-encoded object containing the ID and the time of the stamp. The receipt object gives an estimated time in seconds for the different receipt types \(ethereum and bitcoin\) to be ready for retrieval. Method: POST

> ```text
> {{protocol}}://{{host}}:{{port}}/{{services.notarization}}/users
> ```
>
> ### Headers

| Content-Type | Value |
| :--- | :--- |
| Content-Type | application/x-www-form-urlencoded |

### 🔑 Authentication noauth

| Param | value | Type |
| :--- | :--- | :--- |


⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: Retrieving all stamps

### Description: Retrieves all stamps made by the requesting client, ordered by date, from newest to oldest, paginated in chunks of 50.

You can add ?page=N at the end of the URL in order to show the Nth page. If N is not specified, it is assumed to be 0 and therefore the last 50 stamps are returned.

The response is a JSON-encoded object containing an array of stamps. If a certain receipt found inside a stamp is a number instead of an object, that number is the estimated number of seconds before the final receipt will be ready. Method: GET

> ```text
> {{protocol}}://{{host}}:{{port}}/{{services.notarization}}/stamps
> ```
>
> ### Headers

| Content-Type | Value |
| :--- | :--- |
| Content-Type | application/x-www-form-urlencoded |

⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: blockinfos transactionID

### Description: Retrieves all stamps made by the requesting client, ordered by date, from newest to oldest, paginated in chunks of 50.

You can add ?page=N at the end of the URL in order to show the Nth page. If N is not specified, it is assumed to be 0 and therefore the last 50 stamps are returned.

The response is a JSON-encoded object containing an array of stamps. If a certain receipt found inside a stamp is a number instead of an object, that number is the estimated number of seconds before the final receipt will be ready. Method: GET

> ```text
> {{protocol}}://{{host}}:{{port}}/{{services.notarization}}/blockinfos/transactions/582dfec2972af002022b1a84e0fe2605464846233f4c05edc4e91825f143b9c0
> ```
>
> ### Headers

| Content-Type | Value |
| :--- | :--- |
| Content-Type | application/x-www-form-urlencoded |

⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: blockinfos blockHash

### Description: Retrieves all stamps made by the requesting client, ordered by date, from newest to oldest, paginated in chunks of 50.

You can add ?page=N at the end of the URL in order to show the Nth page. If N is not specified, it is assumed to be 0 and therefore the last 50 stamps are returned.

The response is a JSON-encoded object containing an array of stamps. If a certain receipt found inside a stamp is a number instead of an object, that number is the estimated number of seconds before the final receipt will be ready. Method: GET

> ```text
> http://api.ledgerproject.eu/blockinfos/blocks/hash/48815dc12e627f5ccaea4106a9255a277a95b7c87d5a64d6fb04cc634ba8d4d3
> ```
>
> ### Headers

| Content-Type | Value |
| :--- | :--- |
| Content-Type | application/x-www-form-urlencoded |

⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: blockinfos blockID

### Description: Retrieves all stamps made by the requesting client, ordered by date, from newest to oldest, paginated in chunks of 50.

You can add ?page=N at the end of the URL in order to show the Nth page. If N is not specified, it is assumed to be 0 and therefore the last 50 stamps are returned.

The response is a JSON-encoded object containing an array of stamps. If a certain receipt found inside a stamp is a number instead of an object, that number is the estimated number of seconds before the final receipt will be ready. Method: GET

> ```text
> {{protocol}}://{{host}}:{{port}}/{{services.notarization}}/blockinfos/blocks/3
> ```
>
> ### Headers

| Content-Type | Value |
| :--- | :--- |
| Content-Type | application/x-www-form-urlencoded |

⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: blockinfos

### Description: Retrieves all stamps made by the requesting client, ordered by date, from newest to oldest, paginated in chunks of 50.

You can add ?page=N at the end of the URL in order to show the Nth page. If N is not specified, it is assumed to be 0 and therefore the last 50 stamps are returned.

The response is a JSON-encoded object containing an array of stamps. If a certain receipt found inside a stamp is a number instead of an object, that number is the estimated number of seconds before the final receipt will be ready. Method: GET

> ```text
> {{protocol}}://{{host}}:{{port}}/{{services.notarization}}/blockinfos/stamp/keys/blablabla
> ```
>
> ### Headers

| Content-Type | Value |
| :--- | :--- |
| Content-Type | application/x-www-form-urlencoded |

⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: Retrieving receipts for a stamp

### Description: Retrieves all receipts \(also known as proofs in former Stampery API versions\) for a certain stamp.

The response is a JSON-encoded object containing an array of stamps. If a certain receipt found inside a stamp is a number instead of an object, that number is the estimated number of seconds before the final receipt will be ready. Method: GET

> ```text
> {{protocol}}://{{host}}:{{port}}/{{services.notarization}}/stamp/2f3f3a85340bde09b505b0d37235d1d32a674e43a66229f9a205e7d8d5328ed1
> ```
>
> ### Headers

| Content-Type | Value |
| :--- | :--- |
| Content-Type | application/x-www-form-urlencoded |

⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

