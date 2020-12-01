# Stamp API

{% api-method method="post" host="https://api.token-project.eu" path="/notarization/stamp" %}
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

{% api-method method="get" host="https://api.token-project.eu" path="/notarization/stamp/$STAMP" %}
{% api-method-summary %}
Get a receipt from a HASH
{% endapi-method-summary %}

{% api-method-description %}
Retrieves all receipts \(also known as proofs\) for a certain HASH
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
-H 'Authorization: Bearer $TOKEN'
```

{% api-method method="get" host="https://api.token-project.eu" path="/notarization/blockinfos/stamp/keys/$HASH" %}
{% api-method-summary %}
Get a receipt from a Hash \[DEPRECATED\]
{% endapi-method-summary %}

{% api-method-description %}
Retrieves all receipts \(also known as proofs\) for a certain hash.  
\[DEPRECATED\] Use get /stamp instead
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

{% api-method method="get" host="https://api.token-project.eu" path="/notarization/stamps" %}
{% api-method-summary %}
All stamps
{% endapi-method-summary %}

{% api-method-description %}
Retrieves all stamps made by the requesting client, ordered by date, from newest to oldest.
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
    },
    {
        "docType": "stamp",
        "hash": "2f3f3a85340bde09b505b0d37235d1d32a674e43a66229f9a205e7d8d5328ed16"
    },
    {
        "docType": "stamp",
        "hash": "oiam9yZ2U3NzMiLCJvcmdOYW1lIjoiT3JnMSIsImlhdCI6MTU0OTk5NzU3OX0"
    }
    ...
]
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

