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


{% api-method method="post" host="https://api.token-project.eu" path="/ipfs/block/get" %}
{% api-method-summary %}
Get a raw IPFS block.
{% endapi-method-summary %}

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
The base58 multihash of an existing block to get.
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}

{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```text
� p�B\ �	x�U�0��
ly�RX$hՂ�
�
RI��
�Pǂ8a*�)TEmI̈́W�uFG�u���4-�,*-(�� .o*�B����9��oޤ)8��~����g�<�����s�=��s�=wV�����2���rss�1�Fב��;t8]���9bx��>l���C��G��r�C��5�r�w����Y�������)$++;��\�ٴ��#��ƻ'���s��*>^:������Xx�g��3��N�K�w�Z�S�����g$���䌻���k��b1��8�
5��j}F��Z��������qW}>l�ṙ��s��]K�L�뚧Lq��|�����fq��L��a��?�

(...)

```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}


{% api-method method="post" host="https://api.token-project.eu" path="/ipfs/block/put" %}
{% api-method-summary %}
Store input as an IPFS block.
{% endapi-method-summary %}

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
{% api-method-parameter name="format" type="String" required=false %}
cid format for blocks to be created with.
{% endapi-method-parameter %}
{% api-method-parameter name="mhtype" type="String" required=false %}
multihash hash function. Default: sha2-256.
{% endapi-method-parameter %}
{% api-method-parameter name="mhlen" type="Integer" required=false %}
multihash hash length. Default: -1.
{% endapi-method-parameter %}
{% api-method-parameter name="pin" type="Boolean" required=false %}
pin added blocks recursively. Default: false.
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}

{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```json
{
    "Key": "QmU5NTBAyCNRGvJBbEo2HRdMAncuTDuvScmw3t6Lc1Cb9F",
    "Size": 2813452
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}


{% api-method method="post" host="https://api.token-project.eu" path="/block/stat" %}
{% api-method-summary %}
Print information of a raw IPFS block.
{% endapi-method-summary %}

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
The base58 multihash of an existing block to stat.
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}

{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```json
{
    "Key": "QmU5NTBAyCNRGvJBbEo2HRdMAncuTDuvScmw3t6Lc1Cb9F",
    "Size": 2813452
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}


{% api-method method="post" host="https://api.token-project.eu" path="/ipfs/object/stat" %}
{% api-method-summary %}
Get stats for the DAG node named by.
{% endapi-method-summary %}

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
Key of the object to retrieve, in base58-encoded multihash format.
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
    "Hash": "QmT7iBKicu3dVybBvxzsnffH3xHqV2Eocgr5WcV5AyCQmn",
    "NumLinks": 0,
    "BlockSize": 11,
    "LinksSize": 2,
    "DataSize": 9,
    "CumulativeSize": 11
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}


{% api-method method="post" host="https://api.token-project.eu" path="/ipfs/object/put" %}
{% api-method-summary %}
Store input as a DAG object, print its key.
{% endapi-method-summary %}

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
{% api-method-parameter name="data" type="file" required=true %}
JSON file with format {"Data": "whatever_your_data_is"}
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}

{% api-method-query-parameters %}
{% api-method-parameter name="inputenc" type="String" required=false %}
Encoding type of input data. One of: {"protobuf", "json"}. Default: json.
{% endapi-method-parameter %}
{% api-method-parameter name="datafieldenc" type="String" required=false %}
Encoding type of the data field, either "text" or "base64". Default: text.
{% endapi-method-parameter %}
{% api-method-parameter name="pin" type="Boolean" required=false %}
Pin this object when adding.
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
{
    "Hash": "QmT7iBKicu3dVybBvxzsnffH3xHqV2Eocgr5WcV5AyCQmn"
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}


{% api-method method="post" host="https://api.token-project.eu" path="/ipfs/object/get" %}
{% api-method-summary %}
Get and serialize the DAG node named by.
{% endapi-method-summary %}

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
Key of the object to retrieve, in base58-encoded multihash format.
{% endapi-method-parameter %}
{% api-method-parameter name="data-encoding" type="String" required=false %}
Encoding type of the data field, either "text" or "base64". Default: text.
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}

{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```json
{
    "Links": [],
    "Data": "\b\u0002\u0012\ufffd\ufffd\u0005%PDF-1.4\n%\ufffd\ufffd\ufffd\ufffd\n1 0 obj\n<</Creator (Mozilla/5.0 \\(X11; Linux x86_64\\) AppleWebKit/537.36 \\(KHTML, like Gecko\\) Chrome/86.0.4240.198 Safari/537.36)\n/Producer (Skia/PDF m86)\n/CreationDate (D:20201117135458+00'00')\n/ModDate (D:20201117135458+00'00')>>\nendobj\n3 0 obj\n<</ca 1\n/BM /Normal>>\nendobj\n6 0 obj\n<</CA 1\n/ca 1\n/LC 0\n/LJ 1\n/LW 1\n/ML 4\n/SA true\n/BM /Normal>>\nendobj\n7 0 obj\n<</ca .8471\n/BM /Normal>>\nendobj\n8 0 obj\n<</Type /XObject\n/Subtype /Form\n/Resources <</ProcSet [/PDF /Text /ImageB /ImageC /ImageI]\n/ExtGState <</G6 6 0 R>>>>\n/BBox [0 0 101 104]\n/Group <</Type /Group\n/S /Transparency\n/I true>>\n/Filter /FlateDecode\n/Length 289>> stream\nx\ufffdmR\ufffdn\ufffd0\f\ufffd\ufffd\u0015\ufffd\u000b\ufffd\u0015\ufffd\ufffd\ufffd\u0005\ufffd\ufffd\u000e\ufffd\u0000\ufffd\ufffd\ufffd\u0014H:\ufffd\ufffdCI\ufffd\ufffd\u0000\ufffd`\ufffd\ufffd\ufffd\ufffd$\ufffdW\ufffd\ufffdr\u000e\ufffd\ufffdH\u0012\ufffd(...)"
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}


{% api-method method="post" host="https://api.token-project.eu" path="/ipfs/object/data" %}
{% api-method-summary %}
Output the raw bytes of an IPFS object.
{% endapi-method-summary %}

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
Key of the object to retrieve, in base58-encoded multihash format.
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}

{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```text
��%PDF-1.4
%����
1 0 obj
<</Creator (Mozilla/5.0 \(X11; Linux x86_64\) AppleWebKit/537.36 \(KHTML, like Gecko\) Chrome/86.0.4240.198 Safari/537.36)
/Producer (Skia/PDF m86)
/CreationDate (D:20201117135458+00'00')
/ModDate (D:20201117135458+00'00')>>
endobj
3 0 obj
<</ca 1
/BM /Normal>>
(...)

```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}


{% api-method method="post" host="https://api.token-project.eu" path="/ipfs/get" %}
{% api-method-summary %}
Download IPFS objects.
{% endapi-method-summary %}

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
The path to the IPFS object(s) to be outputted.
{% endapi-method-parameter %}
{% api-method-parameter name="output" type="String" required=false %}
The path where the output should be stored.
{% endapi-method-parameter %}
{% api-method-parameter name="archive" type="Boolean" required=false %}
Output a TAR archive.
{% endapi-method-parameter %}
{% api-method-parameter name="compress" type="Boolean" required=false %}
Compress the output with GZIP compression.
{% endapi-method-parameter %}
{% api-method-parameter name="compression-level" type="Integer" required=false %}
The level of compression (1-9).
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}

{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```text
Qmdok1E4qxJNDfYHFiWetSPXAixqJsYr8gvYwZMuDbNyvd                                                      0000644 0000000 0000000 00000270577 13755241430 017553  0                                                                                                    ustar 00                                                                0000000 0000000                                                                                                                                                                        %PDF-1.4
%����
1 0 obj
<</Creator (Mozilla/5.0 \(X11; Linux x86_64\) AppleWebKit/537.36 \(KHTML, like Gecko\) Chrome/86.0.4240.198 Safari/537.36)
/Producer (Skia/PDF m86)
/CreationDate (D:20201117135458+00'00')
/ModDate (D:20201117135458+00'00')>>
endobj
3 0 obj
<</ca 1
/BM /Normal>>
endobj
6 0 obj
<</CA 1
/ca 1
/LC 0
(...)

```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}


{% api-method method="post" host="https://api.token-project.eu" path="/dag/resolve" %}
{% api-method-summary %}
Resolve ipld block.
{% endapi-method-summary %}

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
The path to resolve.
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}

{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```json
{
    "Cid": {
        "/": "bafyreidh4lnv2aaul7mujtovbjk3l2axylqgynq4knkmcrerjtxskizqvm"
    },
    "RemPath": ""
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}


{% api-method method="post" host="https://api.token-project.eu" path="/ipfs/dag/put" %}
{% api-method-summary %}
Add a dag node to ipfs.
{% endapi-method-summary %}

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
{% api-method-parameter name="object data" type="file" required=true %}
JSON file by default.
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}

{% api-method-query-parameters %}
{% api-method-parameter name="format" type="String" required=false %}
Format that the object will be added as. Default: cbor.
{% endapi-method-parameter %}
{% api-method-parameter name="input-enc" type="String" required=false %}
Format that the input object will be. Default: json.
{% endapi-method-parameter %}
{% api-method-parameter name="pin" type="Boolean" required=false %}
Pin this object when adding.
{% endapi-method-parameter %}
{% api-method-parameter name="hash" type="String" required=false %}
Hash function to use.
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}

{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```json
{
    "Cid": {
        "/": "bafyreidh4lnv2aaul7mujtovbjk3l2axylqgynq4knkmcrerjtxskizqvm"
    }
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}


{% api-method method="post" host="https://api.token-project.eu" path="/dag/get" %}
{% api-method-summary %}
Get a dag node from ipfs.
{% endapi-method-summary %}

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
The object to get.
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}

{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```json
{
    "info": {
        "_id": "73ed9a82-1fd9-4b9c-9a8c-da4675a24fd",
    "protocolProfileBehavior": {}
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}


{% api-method method="post" host="https://api.token-project.eu" path="/cat" %}
{% api-method-summary %}
Show IPFS object data.
{% endapi-method-summary %}

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
The path to the IPFS object(s) to be outputted.
{% endapi-method-parameter %}
{% api-method-parameter name="offset" type="Int64" required=false %}
Byte offset to begin reading from.
{% endapi-method-parameter %}
{% api-method-parameter name="length" type="Int64" required=false %}
Maximum number of bytes to read.
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}

{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```text
%PDF-1.4
%����
1 0 obj
<</Creator (Mozilla/5.0 \(X11; Linux x86_64\) AppleWebKit/537.36 \(KHTML, like Gecko\) Chrome/86.0.4240.198 Safari/537.36)
/Producer (Skia/PDF m86)
/CreationDate (D:20201117135458+00'00')
/ModDate (D:20201117135458+00'00')>>
endobj
3 0 obj
<</ca 1
/BM /Normal>>
endobj
6 0 obj
<</CA 1
/ca 1
/LC 0
/LJ 1
/LW 1
/ML 4
(...)
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}


{% api-method method="post" host="https://api.token-project.eu" path="/ipfs/version" %}
{% api-method-summary %}
Show ipfs version information.
{% endapi-method-summary %}

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
{% api-method-parameter name="number" type="Boolean" required=false %}
Only show the version number.
{% endapi-method-parameter %}
{% api-method-parameter name="commit" type="Boolean" required=false %}
Show the commit hash.
{% endapi-method-parameter %}
{% api-method-parameter name="repo" type="Boolean" required=false %}
Show repo version.
{% endapi-method-parameter %}
{% api-method-parameter name="all" type="Boolean" required=false %}
Show all version information.
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}

{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```json
{
    "Version": "0.4.23",
    "Commit": "5b1687d",
    "Repo": "7",
    "System": "amd64/linux",
    "Golang": "go1.12.16"
}

```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}
