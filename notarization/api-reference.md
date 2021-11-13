# Anchoring API

{% swagger baseUrl="https://api.token-project.eu" path="/notarization/stamp" method="post" summary="Anchor some data" %}
{% swagger-description %}
Creates a timestamp for a given SHA-256 hash hexadecimal digest.
{% endswagger-description %}

{% swagger-parameter name="Content-Type" type="string" required="false" in="header" %}
application/x-www-form-urlencoded
{% endswagger-parameter %}

{% swagger-parameter name="Authorization" type="string" required="true" in="header" %}
Bearer: $TOKEN
{% endswagger-parameter %}

{% swagger-parameter name="hash" type="string" required="true" in="body" %}
SHA-256 hash
{% endswagger-parameter %}

{% swagger-parameter name="data" type="string" required="true" in="body" %}
Data to be anchored
{% endswagger-parameter %}

{% swagger-response status="200" description="" %}
```
{
    "transactionId": "1b9e6cb48098bc1fd8d8bd44c53e92c394c06a41ed50ab5845ed3e8b36e9f012"
}
```
{% endswagger-response %}
{% endswagger %}

```
curl -L -X POST 'https://api.token-project.eu:443/notarization/stamp' \
-H 'Content-Type: application/x-www-form-urlencoded' \
-H 'Authorization: Bearer $TOKEN' \
--data-urlencode 'hash=$HASH'
```

{% swagger baseUrl="https://api.token-project.eu" path="/notarization/stamp/$STAMP" method="get" summary="Get anchored data from a HASH" %}
{% swagger-description %}
Retrieves all anchored data for a certain HASH
{% endswagger-description %}

{% swagger-parameter name="Content-Type" type="string" required="false" in="header" %}
application/x-www-form-urlencoded
{% endswagger-parameter %}

{% swagger-parameter name="Authorization" type="string" required="true" in="header" %}
Bearer: $TOKEN
{% endswagger-parameter %}

{% swagger-response status="200" description="" %}
```
[
    {
        "docType": "stamp",
        "hash": "2f3f3a85340bde09b505b0d37235d1d32a674e43a66229f9a205e7d8d5328ed1",
        "data": "------DATA-----"
    }
]
```
{% endswagger-response %}
{% endswagger %}

```
curl -L -X GET 'https://api.token-project.eu:443/notarization/stamp/$STAMP' \
-H 'Content-Type: application/x-www-form-urlencoded' \
-H 'Authorization: Bearer $TOKEN'
```

{% swagger baseUrl="https://api.token-project.eu" path="/notarization/blockinfos/stamp/keys/$HASH" method="get" summary="Get anchored data from a Hash [DEPRECATED]" %}
{% swagger-description %}
Retrieves all receipts (also known as proofs) for a certain hash.

\


\[DEPRECATED] Use get /stamp instead
{% endswagger-description %}

{% swagger-parameter name="Content-Type" type="string" required="false" in="header" %}
application/x-www-form-urlencoded
{% endswagger-parameter %}

{% swagger-parameter name="Authorization" type="string" required="true" in="header" %}
Bearer: $TOKEN
{% endswagger-parameter %}

{% swagger-response status="200" description="" %}
```
[
    {
        "docType": "stamp",
        "hash": "2f3f3a85340bde09b505b0d37235d1d32a674e43a66229f9a205e7d8d5328ed1",
        "data": "------DATA-----"
    }
]
```
{% endswagger-response %}
{% endswagger %}

```
curl -L -X GET 'https://api.token-project.eu:443/notarization/blockinfos/stamp/keys/$HASH' \
-H 'Content-Type: application/x-www-form-urlencoded' \
-H 'Authorization: Bearer $TOKEN'
```

{% swagger baseUrl="https://api.token-project.eu" path="/notarization/stamps" method="get" summary="All anchors" %}
{% swagger-description %}
Retrieves all anchors made by the requesting client, ordered by date, from newest to oldest.
{% endswagger-description %}

{% swagger-parameter name="Content-Type" type="string" required="false" in="header" %}
application/x-www-form-urlencoded
{% endswagger-parameter %}

{% swagger-parameter name="Authorization" type="string" required="true" in="header" %}
Bearer: $TOKEN
{% endswagger-parameter %}

{% swagger-response status="200" description="" %}
```
[
    {
        "docType": "stamp",
        "hash": "2f3f3a85340bde09b505b0d37235d1d32a674e43a66229f9a205e7d8d5328ed1",
        "data": "------DATA-----"
    },
    {
        "docType": "stamp",
        "hash": "2f3f3a85340bde09b505b0d37235d1d32a674e43a66229f9a205e7d8d5328ed16",
        "data": "------DATA-----"
    },
    {
        "docType": "stamp",
        "hash": "oiam9yZ2U3NzMiLCJvcmdOYW1lIjoiT3JnMSIsImlhdCI6MTU0OTk5NzU3OX0",
        "data": "------DATA-----"
    }
    ...
]
```
{% endswagger-response %}
{% endswagger %}
