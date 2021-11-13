# API reference

## Producing messages

{% swagger baseUrl="https://api.token-project.eu" path="/topics/topic" method="post" summary="Creates a topic" %}
{% swagger-description %}
Creates a topic.
{% endswagger-description %}

{% swagger-parameter name="Content-Type" type="string" required="true" in="header" %}
application/json
{% endswagger-parameter %}

{% swagger-parameter name="Authorization" type="string" required="true" in="header" %}
Bearer: $TOKEN
{% endswagger-parameter %}

{% swagger-parameter name="topic_name" type="string" required="true" in="body" %}
The topic name
{% endswagger-parameter %}

{% swagger-response status="200" description="" %}
```json
{
    "message": "created"
}
```
{% endswagger-response %}
{% endswagger %}

```
curl -L -X POST 'https://api.token-project.eu/streams/topics/topic' \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer $TOKEN' \
--data-raw '{"topic_name": "example"}'
```

{% swagger baseUrl="https://api.token-project.eu" path="/streams/topic/topic_name" method="post" summary="Produces JSON messages to a topic" %}
{% swagger-description %}
Produces JSON messages to a topic
{% endswagger-description %}

{% swagger-parameter name="Content-Type" type="string" required="true" in="header" %}
application/vnd.kafka.json.v2+json
{% endswagger-parameter %}

{% swagger-parameter name="Authorization" type="string" required="true" in="header" %}
Bearer: $TOKEN
{% endswagger-parameter %}

{% swagger-parameter in="body" name="records" type="Array" required="true" %}
Array of JSON Objects
{% endswagger-parameter %}

{% swagger-response status="200" description="" %}
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
{% endswagger-response %}
{% endswagger %}

```
curl -L -X POST 'https://api.token-project.eu/streams/consumers/my_consumer' \
-H 'Content-Type: application/vnd.kafka.json.v2+json' \
-H 'Authorization: Bearer $TOKEN' \
--data-raw '{
    "records": [
        {
            "key":"key",
            "value": {
                "foo": "bar"
            }
        }
    ]
}'
```

## Consuming messages


{% swagger baseUrl="https://api.token-project.eu" path="/streams/consumers/consumer_group" method="post" summary="Creates a new consumer instance" %}
{% swagger-description %}
Creates a new consumer.
{% endswagger-description %}

{% swagger-parameter name="Content-Type" type="string" required="true" in="header" %}
application/vnd.kafka.json.v2+json
{% endswagger-parameter %}

{% swagger-parameter name="Accept" type="string" required="true" in="header" %}
application/vnd.kafka.json.v2+json
{% endswagger-parameter %}

{% swagger-parameter name="Authorization" type="string" required="true" in="header" %}
Bearer: $TOKEN
{% endswagger-parameter %}

{% swagger-parameter name="auto.offset.reset" type="string" required="false" in="body" %}
Sets the auto.offset.reset setting for the consumer
{% endswagger-parameter %}

{% swagger-response status="200" description="" %}
```json
{
    "base_uri": "https://api.token-project.eu/streams/consumers/my_consumer/instances/33707dcc-022d-476e-b8bc-28d0ae2fbb35",
    "instance_id": "33707dcc-022d-476e-b8bc-28d0ae2fbb35"
}
```
{% endswagger-response %}
{% endswagger %}

```
curl -L -X POST 'https://api.token-project.eu/streams/consumers/consumer_group' \
-H 'Content-Type: application/vnd.kafka.json.v2+json' \
-H 'Accept: application/vnd.kafka.json.v2+json' \
-H 'Authorization: Bearer $TOKEN' \
--data-raw '{"auto.offset.reset": "earliest"}'
```


{% swagger baseUrl="https://api.token-project.eu" path="streams/consumers/consumer_group/instances/2eb4ab23-0771-496d-8731-510772c454ab/subscription" method="post" summary="Subscribes the consumer to a topic" %}
{% swagger-description %}
Subscribes the consumer to a topic
{% endswagger-description %}

{% swagger-parameter name="Content-Type" type="string" required="true" in="header" %}
application/vnd.kafka.json.v2+json
{% endswagger-parameter %}

{% swagger-parameter name="Authorization" type="string" required="true" in="header" %}
Bearer: $TOKEN
{% endswagger-parameter %}

{% swagger-parameter in="body" name="topics" type="Array" required="true" %}
Array of topics to subscribe to
{% endswagger-parameter %}

{% swagger-response status="200" description="" %}
```text
Empty response
```
{% endswagger-response %}
{% endswagger %}

```
curl -L -X POST 'https://api.token-project.eu/streams/consumers/consumer_group/instances/2eb4ab23-0771-496d-8731-510772c454ab/subscription' \
-H 'Content-Type: application/vnd.kafka.json.v2+json' \
-H 'Authorization: Bearer $TOKEN' \
--data-raw '{"topics":["messaging"]}'
```


{% swagger baseUrl="https://api.token-project.eu" path="streams/consumers/consumer_group/instances/2eb4ab23-0771-496d-8731-510772c454ab/records" method="get" summary="Consumes messages from a topic" %}
{% swagger-description %}
Consumes messages from a topic
{% endswagger-description %}

{% swagger-parameter name="Accept" type="string" required="true" in="header" %}
application/vnd.kafka.json.v2+json
{% endswagger-parameter %}

{% swagger-parameter name="Authorization" type="string" required="true" in="header" %}
Bearer: $TOKEN
{% endswagger-parameter %}

{% swagger-response status="200" description="" %}
```json
[
  {
    "topic": "topic_name",
    "key":"key",
    "value": {
        "foo": "bar"
    },
    "partition": 0,
    "offset": 0
  },
  {
    "topic": "topic_name",
    "key":"key_1",
    "value": {
        "foo": "bar"
    },
    "partition": 0,
    "offset": 1
  },
  {
    "topic": "topic_name",
    "key":"key_2",
    "value": {
        "foo": "bar"
    },
    "partition": 0,
    "offset": 2
  }
]
```
{% endswagger-response %}
{% endswagger %}

```
curl -L -X GET 'https://api.token-project.eu/streams/consumers/consumer_group/instances/2eb4ab23-0771-496d-8731-510772c454ab/records' \
-H 'Accept: application/vnd.kafka.json.v2+json' \
-H 'Authorization: Bearer $TOKEN' \
--data-raw '{"topics":["messaging"]}'
```
