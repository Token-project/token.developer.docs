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

```text
curl -L -X GET 'https://api.token-project.eu:443/notarization/stamp/$STAMP' \
-H 'Content-Type: application/x-www-form-urlencoded' \
-H 'Authorization: Bearer $TOKEN'
```

{% api-method method="get" host="https://api.ledgerproject.eu" path="/notarization/stamp/$STAMP" %}
{% api-method-summary %}
Get a receipt from a HASH
{% endapi-method-summary %}

{% api-method-description %}
Retrieves all receipts \(also known as proofs\) for a certain stampID
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

{% api-method method="get" host="https://api.ledgerproject.eu" path="/notarization/blockinfos/stamp/keys/$HASH" %}
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

{% api-method method="get" host="https://api.ledgerproject.eu" path="/notarization/stamps" %}
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

```text
curl -L -X GET 'https://api.token-project.eu:443/notarization/blockinfos/stamp/keys/$HASH' \
-H 'Content-Type: application/x-www-form-urlencoded' \
-H 'Authorization: Bearer $TOKEN'
```

```text
curl -L -X GET 'https://api.token-project.eu:443/notarization/blockinfos/transactions/$TRANSACTION_ID' \
-H 'Content-Type: application/x-www-form-urlencoded' \
-H 'Authorization: Bearer $TOKEN'
```

{% api-method method="get" host="https://api.ledgerproject.eu" path="/blockinfos/transactions/$TRANSACTION\_ID" %}
{% api-method-summary %}
Get a transaction detail
{% endapi-method-summary %}

{% api-method-description %}
Retrieves the result of a blockchain transaction
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
{
    "validationCode": 0,
    "transactionEnvelope": {
        "signature": {
            "type": "Buffer",
            "data": [
                48,
                68,
                2,
                32,
                122,
                34,
                73,
                17,
                174,
                89,
                42,
                77,
                205,
                211,
                67,
                131,
                192,
                26,
                252,
                19,
                249,
                56,
                32,
                41,
                80,
                76,
                136,
                102,
                73,
                43,
                167,
                224,
                193,
                64,
                5,
                252,
                2,
                32,
                5,
                0,
                76,
                164,
                130,
                251,
                45,
                236,
                22,
                93,
                53,
                135,
                214,
                11,
                57,
                59,
                244,
                164,
                148,
                120,
                234,
                34,
                255,
                179,
                162,
                28,
                4,
                252,
                67,
                220,
                129,
                42
            ]
        },
        "payload": {
            "header": {
                "channel_header": {
                    "type": 3,
                    "version": 1,
                    "timestamp": "2020-12-01T05:45:03.321Z",
                    "channel_id": "mychannel",
                    "tx_id": "1b9e6cb48098bc1fd8d8bd44c53e92c394c06a41ed50ab5845ed3e8b36e9f012",
                    "epoch": "0",
                    "extension": {
                        "type": "Buffer",
                        "data": [
                            18,
                            5,
                            18,
                            3,
                            116,
                            116,
                            115
                        ]
                    },
                    "typeString": "ENDORSER_TRANSACTION"
                },
                "signature_header": {
                    "creator": {
                        "Mspid": "m-PHY6MR7Z5VFVNHSPBEBSPXEYD4",
                        "IdBytes": "-----BEGIN CERTIFICATE-----\nMIICsDCCAlagAwIBAgIUPFp0MeSI5y/XzJ+LrB8pbNaeAWMwCgYIKoZIzj0EAwIw\ngbMxCzAJBgNVBAYTAlVTMRMwEQYDVQQIEwpXYXNoaW5ndG9uMRAwDgYDVQQHEwdT\nZWF0dGxlMSIwIAYDVQQKExlBbWF6b24gV2ViIFNlcnZpY2VzLCBJbmMuMSIwIAYD\nVQQLExlBbWF6b24gTWFuYWdlZCBCbG9ja2NoYWluMTUwMwYDVQQDEyxtZW1iZXIt\nbmdvIEFtYXpvbiBNYW5hZ2VkIEJsb2NrY2hhaW4gUm9vdCBDQTAeFw0yMDExMjkw\nMDI5MDBaFw0zMDExMjcwMDM0MDBaMDQxIjANBgNVBAsTBmNsaWVudDARBgNVBAsT\nCm1lbWJlci1uZ28xDjAMBgNVBAMTBXRva2VuMFkwEwYHKoZIzj0CAQYIKoZIzj0D\nAQcDQgAEJ6alHTkHIKZMfxj/pso2uID+llYZ+C7L7cf36yTPJzBgGsvoSsdLcbMV\nRSyyOntRiZ5d6Ji62MIM/DstzpwyOqOBxTCBwjAOBgNVHQ8BAf8EBAMCB4AwDAYD\nVR0TAQH/BAIwADAdBgNVHQ4EFgQUH/wH3TeLq7WowoixWf4M/2u/TtowHwYDVR0j\nBBgwFoAUxzX1DV8mR9eMqV432VvNHwLt098wYgYIKgMEBQYHCAEEVnsiYXR0cnMi\nOnsiaGYuQWZmaWxpYXRpb24iOiJtZW1iZXItbmdvIiwiaGYuRW5yb2xsbWVudElE\nIjoidG9rZW4iLCJoZi5UeXBlIjoiY2xpZW50In19MAoGCCqGSM49BAMCA0gAMEUC\nIQC7m5hlc2MM4qT2p41MUsJFQPaaBZgCfuXUsMPSXnZamQIgVwGA1WdUQR3sCNL7\nFqwTwzC/am/mUOm5KVn2mqPOrl4=\n-----END CERTIFICATE-----\n"
                    },
                    "nonce": {
                        "type": "Buffer",
                        "data": [
                            3,
                            33,
                            239,
                            113,
                            201,
                            219,
                            37,
                            110,
                            93,
                            116,
                            154,
                            150,
                            93,
                            129,
                            54,
                            173,
                            7,
                            240,
                            44,
                            239,
                            111,
                            42,
                            104,
                            77
                        ]
                    }
                }
            },
            "data": {
                "actions": [
                    {
                        "header": {
                            "creator": {
                                "Mspid": "m-PHY6MR7Z5VFVNHSPBEBSPXEYD4",
                                "IdBytes": "-----BEGIN CERTIFICATE-----\nMIICsDCCAlagAwIBAgIUPFp0MeSI5y/XzJ+LrB8pbNaeAWMwCgYIKoZIzj0EAwIw\ngbMxCzAJBgNVBAYTAlVTMRMwEQYDVQQIEwpXYXNoaW5ndG9uMRAwDgYDVQQHEwdT\nZWF0dGxlMSIwIAYDVQQKExlBbWF6b24gV2ViIFNlcnZpY2VzLCBJbmMuMSIwIAYD\nVQQLExlBbWF6b24gTWFuYWdlZCBCbG9ja2NoYWluMTUwMwYDVQQDEyxtZW1iZXIt\nbmdvIEFtYXpvbiBNYW5hZ2VkIEJsb2NrY2hhaW4gUm9vdCBDQTAeFw0yMDExMjkw\nMDI5MDBaFw0zMDExMjcwMDM0MDBaMDQxIjANBgNVBAsTBmNsaWVudDARBgNVBAsT\nCm1lbWJlci1uZ28xDjAMBgNVBAMTBXRva2VuMFkwEwYHKoZIzj0CAQYIKoZIzj0D\nAQcDQgAEJ6alHTkHIKZMfxj/pso2uID+llYZ+C7L7cf36yTPJzBgGsvoSsdLcbMV\nRSyyOntRiZ5d6Ji62MIM/DstzpwyOqOBxTCBwjAOBgNVHQ8BAf8EBAMCB4AwDAYD\nVR0TAQH/BAIwADAdBgNVHQ4EFgQUH/wH3TeLq7WowoixWf4M/2u/TtowHwYDVR0j\nBBgwFoAUxzX1DV8mR9eMqV432VvNHwLt098wYgYIKgMEBQYHCAEEVnsiYXR0cnMi\nOnsiaGYuQWZmaWxpYXRpb24iOiJtZW1iZXItbmdvIiwiaGYuRW5yb2xsbWVudElE\nIjoidG9rZW4iLCJoZi5UeXBlIjoiY2xpZW50In19MAoGCCqGSM49BAMCA0gAMEUC\nIQC7m5hlc2MM4qT2p41MUsJFQPaaBZgCfuXUsMPSXnZamQIgVwGA1WdUQR3sCNL7\nFqwTwzC/am/mUOm5KVn2mqPOrl4=\n-----END CERTIFICATE-----\n"
                            },
                            "nonce": {
                                "type": "Buffer",
                                "data": [
                                    3,
                                    33,
                                    239,
                                    113,
                                    201,
                                    219,
                                    37,
                                    110,
                                    93,
                                    116,
                                    154,
                                    150,
                                    93,
                                    129,
                                    54,
                                    173,
                                    7,
                                    240,
                                    44,
                                    239,
                                    111,
                                    42,
                                    104,
                                    77
                                ]
                            }
                        },
                        "payload": {
                            "chaincode_proposal_payload": {
                                "input": {
                                    "chaincode_spec": {
                                        "type": 1,
                                        "typeString": "GOLANG",
                                        "input": {
                                            "args": [
                                                {
                                                    "type": "Buffer",
                                                    "data": [
                                                        99,
                                                        114,
                                                        101,
                                                        97,
                                                        116,
                                                        101,
                                                        83,
                                                        116,
                                                        97,
                                                        109,
                                                        112
                                                    ]
                                                },
                                                {
                                                    "type": "Buffer",
                                                    "data": [
                                                        123,
                                                        34,
                                                        104,
                                                        97,
                                                        115,
                                                        104,
                                                        34,
                                                        58,
                                                        34,
                                                        111,
                                                        105,
                                                        97,
                                                        109,
                                                        57,
                                                        121,
                                                        90,
                                                        50,
                                                        85,
                                                        51,
                                                        78,
                                                        122,
                                                        77,
                                                        105,
                                                        76,
                                                        67,
                                                        74,
                                                        118,
                                                        99,
                                                        109,
                                                        100,
                                                        79,
                                                        89,
                                                        87,
                                                        49,
                                                        108,
                                                        73,
                                                        106,
                                                        111,
                                                        105,
                                                        84,
                                                        51,
                                                        74,
                                                        110,
                                                        77,
                                                        83,
                                                        73,
                                                        115,
                                                        73,
                                                        109,
                                                        108,
                                                        104,
                                                        100,
                                                        67,
                                                        73,
                                                        54,
                                                        77,
                                                        84,
                                                        85,
                                                        48,
                                                        79,
                                                        84,
                                                        107,
                                                        53,
                                                        78,
                                                        122,
                                                        85,
                                                        51,
                                                        79,
                                                        88,
                                                        48,
                                                        34,
                                                        125
                                                    ]
                                                }
                                            ],
                                            "decorations": {}
                                        },
                                        "chaincode_id": {
                                            "path": "",
                                            "name": "tts",
                                            "version": ""
                                        },
                                        "timeout": 0
                                    }
                                }
                            },
                            "action": {
                                "proposal_response_payload": {
                                    "proposal_hash": "86a6a8622b91ca2c7414b400190280b2e527f65fb7281b4ea844b3bf57c9adb9",
                                    "extension": {
                                        "results": {
                                            "data_model": 0,
                                            "ns_rwset": [
                                                {
                                                    "namespace": "lscc",
                                                    "rwset": {
                                                        "reads": [
                                                            {
                                                                "key": "tts",
                                                                "version": {
                                                                    "block_num": "1",
                                                                    "tx_num": "0"
                                                                }
                                                            }
                                                        ],
                                                        "range_queries_info": [],
                                                        "writes": [],
                                                        "metadata_writes": []
                                                    },
                                                    "collection_hashed_rwset": []
                                                },
                                                {
                                                    "namespace": "tts",
                                                    "rwset": {
                                                        "reads": [
                                                            {
                                                                "key": "stampoiam9yZ2U3NzMiLCJvcmdOYW1lIjoiT3JnMSIsImlhdCI6MTU0OTk5NzU3OX0",
                                                                "version": null
                                                            }
                                                        ],
                                                        "range_queries_info": [],
                                                        "writes": [
                                                            {
                                                                "key": "stampoiam9yZ2U3NzMiLCJvcmdOYW1lIjoiT3JnMSIsImlhdCI6MTU0OTk5NzU3OX0",
                                                                "is_delete": false,
                                                                "value": "{\"hash\":\"oiam9yZ2U3NzMiLCJvcmdOYW1lIjoiT3JnMSIsImlhdCI6MTU0OTk5NzU3OX0\",\"docType\":\"stamp\"}"
                                                            }
                                                        ],
                                                        "metadata_writes": []
                                                    },
                                                    "collection_hashed_rwset": []
                                                }
                                            ]
                                        },
                                        "events": {
                                            "chaincode_id": "",
                                            "tx_id": "",
                                            "event_name": "",
                                            "payload": {
                                                "type": "Buffer",
                                                "data": []
                                            }
                                        },
                                        "response": {
                                            "status": 200,
                                            "message": "",
                                            "payload": ""
                                        },
                                        "chaincode_id": {
                                            "path": "",
                                            "name": "tts",
                                            "version": "1"
                                        }
                                    }
                                },
                                "endorsements": [
                                    {
                                        "endorser": {
                                            "Mspid": "m-PHY6MR7Z5VFVNHSPBEBSPXEYD4",
                                            "IdBytes": "-----BEGIN CERTIFICATE-----\nMIIDTDCCAvKgAwIBAgIUOd0VjNw/eO1DYbYVmf+AzGMKSiowCgYIKoZIzj0EAwIw\ngbMxCzAJBgNVBAYTAlVTMRMwEQYDVQQIEwpXYXNoaW5ndG9uMRAwDgYDVQQHEwdT\nZWF0dGxlMSIwIAYDVQQKExlBbWF6b24gV2ViIFNlcnZpY2VzLCBJbmMuMSIwIAYD\nVQQLExlBbWF6b24gTWFuYWdlZCBCbG9ja2NoYWluMTUwMwYDVQQDEyxtZW1iZXIt\nbmdvIEFtYXpvbiBNYW5hZ2VkIEJsb2NrY2hhaW4gUm9vdCBDQTAeFw0yMDExMjgy\nMTQ1MDBaFw0zMDExMjYyMTUwMDBaMIGLMQswCQYDVQQGEwJVUzEXMBUGA1UECBMO\nTm9ydGggQ2Fyb2xpbmExFDASBgNVBAoTC0h5cGVybGVkZ2VyMSAwCwYDVQQLEwRw\nZWVyMBEGA1UECxMKbWVtYmVyLW5nbzErMCkGA1UEAxMicGVlci1uZC1URE43UDM1\nU1FOQ0ZKTElVM1dFTFZUNzc2WTBZMBMGByqGSM49AgEGCCqGSM49AwEHA0IABNKr\nGx4mx05DNiJ9IfKgeDL3VV+HB+ML/WclwMo17PfRYqhkW36zqZF9Efj95tC4kF6E\ncgxGZz1PJ72L4qPZFPmjggEIMIIBBDAOBgNVHQ8BAf8EBAMCB4AwDAYDVR0TAQH/\nBAIwADAdBgNVHQ4EFgQUYwEYxqhfVw2EibgUfmkbFIpNLh8wHwYDVR0jBBgwFoAU\nxzX1DV8mR9eMqV432VvNHwLt098wJQYDVR0RBB4wHIIaaXAtMTAtMC0xLTE3Mi5l\nYzIuaW50ZXJuYWwwfQYIKgMEBQYHCAEEcXsiYXR0cnMiOnsiaGYuQWZmaWxpYXRp\nb24iOiJtZW1iZXItbmdvIiwiaGYuRW5yb2xsbWVudElEIjoicGVlci1uZC1URE43\nUDM1U1FOQ0ZKTElVM1dFTFZUNzc2WSIsImhmLlR5cGUiOiJwZWVyIn19MAoGCCqG\nSM49BAMCA0gAMEUCIQDWggviLtU2B1xgz3/Oxyw8H+od37iwQAGXkZsXXWtbSAIg\nIGJQ/L2tNjru9jkdMvXVpZBVJzytI+TOE957TEOsqd4=\n-----END CERTIFICATE-----\n"
                                        },
                                        "signature": {
                                            "type": "Buffer",
                                            "data": [
                                                48,
                                                69,
                                                2,
                                                33,
                                                0,
                                                220,
                                                124,
                                                131,
                                                147,
                                                157,
                                                140,
                                                151,
                                                95,
                                                32,
                                                174,
                                                207,
                                                215,
                                                175,
                                                12,
                                                115,
                                                244,
                                                85,
                                                215,
                                                16,
                                                237,
                                                110,
                                                48,
                                                71,
                                                132,
                                                89,
                                                41,
                                                231,
                                                105,
                                                127,
                                                65,
                                                70,
                                                85,
                                                2,
                                                32,
                                                24,
                                                97,
                                                192,
                                                124,
                                                150,
                                                206,
                                                97,
                                                140,
                                                148,
                                                59,
                                                127,
                                                174,
                                                188,
                                                130,
                                                60,
                                                92,
                                                60,
                                                4,
                                                54,
                                                155,
                                                36,
                                                158,
                                                182,
                                                249,
                                                147,
                                                36,
                                                130,
                                                186,
                                                135,
                                                53,
                                                198,
                                                7
                                            ]
                                        }
                                    }
                                ]
                            }
                        }
                    }
                ]
            }
        }
    }
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

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

