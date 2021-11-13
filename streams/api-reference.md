# Anchoring API

{% api-method method="post" host="https://api.token-project.eu" path="/topics/topic" %}
{% api-method-summary %}
Creates a topic
{% endapi-method-summary %}

{% api-method-description %}
Creates a topic.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Content-Type" type="string" required=true %}
application/json
{% endapi-method-parameter %}
{% api-method-parameter name="Authorization" type="string" required=true %}
Bearer: $TOKEN
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-body-parameters %}
{% api-method-parameter name="topic_name" type="string" required=true %}
The topic name
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```json
{
    "message": "created"
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

```text
curl -L -X POST 'https://api.token-project.eu:443/topics/topic' \
-H 'Authorization: Bearer $TOKEN' \
--data-raw '{"topic_name": "example"}'
```