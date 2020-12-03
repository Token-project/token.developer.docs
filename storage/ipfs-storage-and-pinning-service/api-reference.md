# API reference

{% api-method method="post" host="https://api.token-project.eu" path="/ipfs/add" %}
{% api-method-summary %}
Adds content to the IPFS daemon.
{% endapi-method-summary %}

{% api-method-description %}
The proxy adds the content to the local IPFS daemon and pins the resulting hash\[es\] in cluster.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Content-Type" type="string" required=false %}
application/form-data
{% endapi-method-parameter %}

{% api-method-parameter name="Authorization" type="string" required=true %}
Bearer: $TOKEN
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-body-parameters %}
{% api-method-parameter name="path" type="file" required=true %}
File to upload
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}

{% api-method-query-parameters %}
{% api-method-parameter name="quiet" type="Boolean" required=false %}
Write minimal output.
{% endapi-method-parameter %}
{% api-method-parameter name="quieter" type="Boolean" required=false %}
Write only final hash.
{% endapi-method-parameter %}
{% api-method-parameter name="silent" type="Boolean" required=false %}
Write no output.
{% endapi-method-parameter %}
{% api-method-parameter name="progress" type="Boolean" required=false %}
Stream progress data.
{% endapi-method-parameter %}
{% api-method-parameter name="trickle" type="Boolean" required=false %}
Use trickle-dag format for dag generation.
{% endapi-method-parameter %}
{% api-method-parameter name="only-hash" type="Boolean" required=false %}
Only chunk and hash - do not write to disk.
{% endapi-method-parameter %}
{% api-method-parameter name="wrap-with-directory" type="Boolean" required=false %}
Wrap files with a directory object.
{% endapi-method-parameter %}
{% api-method-parameter name="chunker" type="String" required=false %}
Chunking algorithm, size-\[bytes\], rabin-\[min\]-\[avg\]-\[max\] or buzhash. Default: size-262144.
{% endapi-method-parameter %}
{% api-method-parameter name="pin" type="Boolean" required=false %}
Pin this object when adding. Default: true. 
{% endapi-method-parameter %}
{% api-method-parameter name="raw-leaves" type="Boolean" required=false %}
Use raw blocks for leaf nodes. (experimental).
{% endapi-method-parameter %}
{% api-method-parameter name="nocopy" type="Boolean" required=false %}
Add the file using filestore. Implies raw-leaves. (experimental).
{% endapi-method-parameter %}
{% api-method-parameter name="fscache" type="Boolean" required=false %}
Check the filestore for pre-existing blocks. (experimental).
{% endapi-method-parameter %}
{% api-method-parameter name="cid-version" type="Integer" required=false %}
CID version. Defaults to 0 unless an option that depends on CIDv1 is passed (experimental).
{% endapi-method-parameter %}
{% api-method-parameter name="hash" type="String" required=false %}
Hash function to use. Implies CIDv1 if not sha2-256. (experimental). Default: sha2-256.
{% endapi-method-parameter %}
{% api-method-parameter name="inline" type="Boolean" required=false %}
Inline small blocks into CIDs. (experimental).
{% endapi-method-parameter %}
{% api-method-parameter name="inline-limit" type="Integer" required=false %}
Maximum block size to inline. (experimental). Default: 32.
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}

{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```json
{
    "Name": "test.json",
    "Hash": "QmPcCSG7rDNLB2x6P95MZtEK8FopV82b4997pKLzYyFaLE",
    "Size": "31"
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}


{% api-method method="post" host="https://api.token-project.eu" path="/ipfs/pin/add" %}
{% api-method-summary %}
Pin given CID in the cluster.
{% endapi-method-summary %}

{% api-method-description %}
The proxy pins the given CID in the cluster.
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

{% api-method-query-parameters %}
{% api-method-parameter name="arg" type="String" required=true %}
Path to object(s) to be pinned.
{% endapi-method-parameter %}
{% api-method-parameter name="progress" type="Boolean" required=false %}
Show progress.
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}

{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```json
{
    "Pins": [
        "QmPcCSG7rDNLB2x6P95MZtEK8FopV82b4997pKLzYyFaLE"
    ]
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}


{% api-method method="post" host="https://api.token-project.eu" path="/ipfs/pin/update" %}
{% api-method-summary %}
Update given pin to a new one.
{% endapi-method-summary %}

{% api-method-description %}
The proxy updates the given pin to a new one in cluster.
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

{% api-method-query-parameters %}
{% api-method-parameter name="arg" type="String" required=true %}
Path to old object.
{% endapi-method-parameter %}
{% api-method-parameter name="arg" type="String" required=true %}
Path to a new object to be pinned.
{% endapi-method-parameter %}
{% api-method-parameter name="unpin" type="Boolean" required=false %}
Remove the old pin. Default: true.
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}

{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```json
{
    "Pins": [
        "QmPcCSG7rDNLB2x6P95MZtEK8FopV82b4997pKLzYyFaLE",
        "QmchBjNsmCXys1kQSkzyAS1Phxq3mg5kC3qhuYGPPKDqh8"
    ]
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}


{% api-method method="post" host="https://api.token-project.eu" path="/ipfs/pin/rm" %}
{% api-method-summary %}
Unpin given CID from cluster.
{% endapi-method-summary %}

{% api-method-description %}
The proxy unpins the given CID from cluster.
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

{% api-method-query-parameters %}
{% api-method-parameter name="arg" type="String" required=true %}
Path to object(s) to be unpinned.
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}

{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```json
{
    "Pins": [
        "QmchBjNsmCXys1kQSkzyAS1Phxq3mg5kC3qhuYGPPKDqh8"
    ]
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}


{% api-method method="post" host="https://api.token-project.eu" path="/ipfs/pin/ls" %}
{% api-method-summary %}
List the pinned items in cluster.
{% endapi-method-summary %}

{% api-method-description %}
The proxy lists the pinned items in cluster.
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

{% api-method-query-parameters %}
{% api-method-parameter name="arg" type="String" required=true %}
Path to object(s) to be listed.
{% endapi-method-parameter %}
{% api-method-parameter name="type" type="String" required=true %}
The type of pinned keys to list. Can be "direct", "indirect", "recursive", or "all". Default: all.
{% endapi-method-parameter %}
{% api-method-parameter name="quiet" type="Boolean" required=true %}
Write just hashes of objects.
{% endapi-method-parameter %}
{% api-method-parameter name="stream" type="Boolean" required=true %}
Enable streaming of pins as they are discovered.
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}

{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```json
{
    "Keys": {
        "QmPcCSG7rDNLB2x6P95MZtEK8FopV82b4997pKLzYyFaLE": {
            "Type": "recursive"
        }
    }
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}


{% api-method method="post" host="https://api.token-project.eu" path="/ipfs/repo/stat" %}
{% api-method-summary %}
Aggregated /repo/stat from all connected daemons.
{% endapi-method-summary %}

{% api-method-description %}
The proxy responds with aggregated /repo/stat from all connected IPFS daemons.
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

{% api-method-query-parameters %}
{% api-method-parameter name="size-only" type="Boolean" required=false %}
Only report RepoSize and StorageMax.
{% endapi-method-parameter %}
{% api-method-parameter name="human" type="Boolean" required=false %}
Print sizes in human readable format (e.g., 1K 234M 2G).
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}

{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```json
{
    "RepoSize": 121213387,
    "StorageMax": 30000000000
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}


{% api-method method="post" host="https://api.token-project.eu" path="/ipfs/repo/gc" %}
{% api-method-summary %}
Garbage collection on all IPFS daemons
{% endapi-method-summary %}

{% api-method-description %}
The proxy performs garbage collection on all IPFS daemons and responds with collected CIDs.
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

{% api-method-query-parameters %}
{% api-method-parameter name="stream-errors" type="Boolean" required=false %}
Stream errors.
{% endapi-method-parameter %}
{% api-method-parameter name="quiet" type="Boolean" required=false %}
Write minimal output.
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}

{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```json
{"Key":{"/":"Qmd1Drph9zkL7TLPfzGFLESjLniuv4n2cMsfXbikdV4QA7"}}
{"Key":{"/":"QmR9xMynmwLqNJkuwXe4aN1EkhkkqUbbTzCCbWxehEKHyk"}}
{"Key":{"/":"bafyreidh4lnv2aaul7mujtovbjk3l2axylqgynq4knkmcrerjtxskizqvm"}}

```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

### End-point: /block/get

#### Description: Get a raw IPFS block.

Method: POST

> ```text
> https://api.token-project.eu/ipfs/block/get?arg=String
> ```
>
> #### Query Params

| Param | value |
| :--- | :--- |
| arg | String |

⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

### End-point: /block/put

#### Description: Store input as an IPFS block.

Method: POST

> ```text
> https://api.token-project.eu/ipfs/block/put?format=String&mhtype=String&mhlen=Integer&pin=Boolean
> ```
>
> #### Body formdata

| Param | value | Type |
| :--- | :--- | :--- |
| data |  | file |

#### Query Params

| Param | value |
| :--- | :--- |
| format | String |
| mhtype | String |
| mhlen | Integer |
| pin | Boolean |

⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

### End-point: /version

#### Description: Show ipfs version information.

Method: POST

> ```text
> https://api.token-project.eu/ipfs/version?number=Boolean&commit=Boolean&repo=Boolean&all=Boolean
> ```
>
> #### Query Params

| Param | value |
| :--- | :--- |
| number | Boolean |
| commit | Boolean |
| repo | Boolean |
| all | Boolean |

⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃



### End-point: /object/stat

#### Description: Get stats for the DAG node named by .

Method: POST

> ```text
> https://api.token-project.eu/ipfs/object/stat?arg=String&human=Boolean
> ```
>
> #### Query Params

| Param | value |
| :--- | :--- |
| arg | String |
| human | Boolean |

⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

### End-point: /object/put

#### Description: Store input as a DAG object, print its key.

Method: POST

> ```text
> https://api.token-project.eu/ipfs/object/put?inputenc=String&datafieldenc=String&pin=Boolean&quiet=Boolean
> ```
>
> #### Body formdata

| Param | value | Type |
| :--- | :--- | :--- |
| data |  | file |

#### Query Params

| Param | value |
| :--- | :--- |
| inputenc | String |
| datafieldenc | String |
| pin | Boolean |
| quiet | Boolean |

⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

### End-point: /object/get

#### Description: Get and serialize the DAG node named by .

Method: POST

> ```text
> https://api.token-project.eu/ipfs/object/get?arg=String&data-encoding=String
> ```
>
> #### Query Params

| Param | value |
| :--- | :--- |
| arg | String |
| data-encoding | String |

⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

### End-point: /object/data

#### Description: Output the raw bytes of an IPFS object.

Method: POST

> ```text
> https://api.token-project.eu/ipfs/object/data?arg=String
> ```
>
> #### Query Params

| Param | value |
| :--- | :--- |
| arg | String |

⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

### End-point: /get

#### Description: Download IPFS objects.

Method: POST

> ```text
> https://api.token-project.eu/auth/token?key=LJHyxcBqWKLhZdxZo9X5yBFvJQpWYfCT&secret=vbQ6esJgef9ktKymZ9HKKmMaHZCLRmGN
> ```
>
> #### Query Params

| Param | value |
| :--- | :--- |
| key | LJHyxcBqWKLhZdxZo9X5yBFvJQpWYfCT |
| secret | vbQ6esJgef9ktKymZ9HKKmMaHZCLRmGN |
| archive | true |

#### 🔑 Authentication bearer

| Param | value | Type |
| :--- | :--- | :--- |
| token |  | string |

⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

### End-point: /dag/resolve

#### Description: Resolve ipld block

Method: POST

> ```text
> https://api.token-project.eu/ipfs/dag/resolve?arg=String
> ```
>
> #### Query Params

| Param | value |
| :--- | :--- |
| arg | String |

⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

### End-point: /dag/put

#### Description: Add a dag node to ipfs.

Method: POST

> ```text
> https://api.token-project.eu/ipfs/dag/put?format=String&input-enc=String&pin=Boolean&hash=String
> ```
>
> #### Body formdata

| Param | value | Type |
| :--- | :--- | :--- |
| object data |  | file |

#### Query Params

| Param | value |
| :--- | :--- |
| format | String |
| input-enc | String |
| pin | Boolean |
| hash | String |

⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

### End-point: /dag/get

#### Description: Get a dag node from ipfs.

Method: POST

> ```text
> https://api.token-project.eu/ipfs/dag/get?arg=String
> ```
>
> #### Query Params

| Param | value |
| :--- | :--- |
| arg | String |

⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

### End-point: /cat

#### Description: Show IPFS object data.

Method: POST

> ```text
> https://api.token-project.eu/ipfs/cat?arg=String&offset=Int64&length=Int64
> ```
>
> #### Query Params

| Param | value |
| :--- | :--- |
| arg | String |
| offset | Int64 |
| length | Int64 |

⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

### End-point: /block/stat

#### Description: Print information of a raw IPFS block.

Method: POST

> ```text
> https://api.token-project.eu/ipfs/block/stat?arg=String
> ```
>
> #### Query Params

| Param | value |
| :--- | :--- |
| arg | String |

⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃









