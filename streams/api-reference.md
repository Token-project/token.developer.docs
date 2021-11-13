# Streams API

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
curl -L -X POST 'https://api.token-project.eu/streams/topics/topic' \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer $TOKEN' \
--data-raw '{"topic_name": "example"}'
```


{% api-method method="post" host="https://api.token-project.eu" path="consumers/my_consumer" %}
{% api-method-summary %}
Creates a new consumer instance
{% endapi-method-summary %}

{% api-method-description %}
Creates a new consumer.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Content-Type" type="string" required=true %}
application/vnd.kafka.json.v2+json
{% endapi-method-parameter %}
{% api-method-parameter name="Accept" type="string" required=true %}
application/vnd.kafka.json.v2+json
{% endapi-method-parameter %}
{% api-method-parameter name="Authorization" type="string" required=true %}
Bearer: $TOKEN
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-body-parameters %}
{% api-method-parameter name="auto.offset.reset" type="string" required=false %}
Sets the auto.offset.reset setting for the consumer
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```json
{
    "base_uri": "https://api.token-project.eu/streams/consumers/my_consumer/instances/33707dcc-022d-476e-b8bc-28d0ae2fbb35",
    "instance_id": "33707dcc-022d-476e-b8bc-28d0ae2fbb35"
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

```text
curl -L -X POST 'https://api.token-project.eu/streams/consumers/consumer_group' \
-H 'Content-Type: application/vnd.kafka.json.v2+json' \
-H 'Accept: application/vnd.kafka.json.v2+json' \
-H 'Authorization: Bearer $TOKEN' \
--data-raw '{"auto.offset.reset": "earliest"}'
```



{% api-method method="post" host="https://api.token-project.eu" path="topic/topic_name" %}
{% api-method-summary %}
Produces JSON messages to a topic
{% endapi-method-summary %}

{% api-method-description %}
Produces JSON messages to a topic
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Content-Type" type="string" required=true %}
application/vnd.kafka.json.v2+json
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

```json
{
    "offsets": [
        {
            "offset": 1,
            "partition": 0
        }
    ]
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

```text
curl -L -X POST 'https://api.token-project.eu/streams/consumers/my_consumer' \
-H 'Content-Type: application/vnd.kafka.json.v2+json' \
-H 'Authorization: Bearer $TOKEN' \
--data-raw '{
    "records": [
        {
            "value": {
                "foo": "bar"
            }
        }
    ]
}'
```
