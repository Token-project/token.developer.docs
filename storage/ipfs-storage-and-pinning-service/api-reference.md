# API reference

## 📁 Collection: IPFS Cluster Proxy

### End-point: /add

#### Description: The proxy adds the content to the local ipfs daemon and pins the resulting hash\[es\] in cluster.

Method: POST

> ```text
> /api/v0/add?quiet=Boolean&quieter=Boolean&silent=Boolean&progress=Boolean&trickle=Boolean&only-hash=Boolean&wrap-with-directory=Boolean&chunker=String&pin=Boolean&raw-leaves=Boolean&nocopy=Boolean&fscache=Boolean&cid-version=Integer&hash=String&inline=Boolean&inline-limit=Integer
> ```
>
> #### Body formdata

| Param | value | Type |
| :--- | :--- | :--- |
| path |  | file |

#### Query Params

| Param | value |
| :--- | :--- |
| quiet | Boolean |
| quieter | Boolean |
| silent | Boolean |
| progress | Boolean |
| trickle | Boolean |
| only-hash | Boolean |
| wrap-with-directory | Boolean |
| chunker | String |
| pin | Boolean |
| raw-leaves | Boolean |
| nocopy | Boolean |
| fscache | Boolean |
| cid-version | Integer |
| hash | String |
| inline | Boolean |
| inline-limit | Integer |

⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

### End-point: /pin/add

#### Description: The proxy pins the given CID in cluster.

Method: POST

> ```text
> /api/v0/pin/add?arg=String&progress=Boolean
> ```
>
> #### Query Params

| Param | value |
| :--- | :--- |
| arg | String |
| progress | Boolean |

⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

### End-point: /pin/update

#### Description: The proxy updates the given pin to a new one in cluster.

Method: POST

> ```text
> /api/v0/pin/update?arg=String&arg=String&unpin=Boolean
> ```
>
> #### Query Params

| Param | value |
| :--- | :--- |
| arg | String |
| arg | String |
| unpin | Boolean |

⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

### End-point: /pin/rm

#### Description: The proxy unpins the given CID from cluster.

Method: POST

> ```text
> /api/v0/pin/rm?arg=String
> ```
>
> #### Query Params

| Param | value |
| :--- | :--- |
| arg | String |

⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

### End-point: /repo/stat

#### Description: The proxy responds with aggregated /repo/stat from all connected IPFS daemons.

Method: POST

> ```text
> /api/v0/repo/stat?size-only=Boolean&human=Boolean
> ```
>
> #### Query Params

| Param | value |
| :--- | :--- |
| size-only | Boolean |
| human | Boolean |

⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

### End-point: /pin/ls

#### Description: The proxy lists the pinned items in cluster.

Method: POST

> ```text
> /api/v0/pin/ls?arg=String&type=String&quiet=Boolean&stream=Boolean
> ```
>
> #### Query Params

| Param | value |
| :--- | :--- |
| arg | String |
| type | String |
| quiet | Boolean |
| stream | Boolean |

⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

### End-point: /repo/gc

#### Description: The proxy performs garbage collection on all IPFS daemons and responds with collected CIDs.

Method: POST

> ```text
> /api/v0/repo/gc?stream-errors=Boolean&quiet=Boolean
> ```
>
> #### Query Params

| Param | value |
| :--- | :--- |
| stream-errors | Boolean |
| quiet | Boolean |

⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃



## 📁 Collection: IPFS

### End-point: /add

#### Description: Add a file or directory to ipfs.

Method: POST

> ```text
> {{protocol}}://{{host}}:{{port}}/{{services.ipfs}}/add?quiet=Boolean&quieter=Boolean&silent=Boolean&progress=Boolean&trickle=Boolean&only-hash=Boolean&wrap-with-directory=Boolean&chunker=String&pin=Boolean&raw-leaves=Boolean&nocopy=Boolean&fscache=Boolean&cid-version=Integer&hash=String&inline=Boolean&inline-limit=Integer
> ```
>
> #### Body formdata

| Param | value | Type |
| :--- | :--- | :--- |
| path |  | file |

#### Query Params

| Param | value |
| :--- | :--- |
| quiet | Boolean |
| quieter | Boolean |
| silent | Boolean |
| progress | Boolean |
| trickle | Boolean |
| only-hash | Boolean |
| wrap-with-directory | Boolean |
| chunker | String |
| pin | Boolean |
| raw-leaves | Boolean |
| nocopy | Boolean |
| fscache | Boolean |
| cid-version | Integer |
| hash | String |
| inline | Boolean |
| inline-limit | Integer |

⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

### End-point: /block/get

#### Description: Get a raw IPFS block.

Method: POST

> ```text
> /api/v0/block/get?arg=String
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
> /api/v0/block/put?format=String&mhtype=String&mhlen=Integer&pin=Boolean
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
> /api/v0/version?number=Boolean&commit=Boolean&repo=Boolean&all=Boolean
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

### End-point: /pin/add

#### Description: Pin objects to local storage.

Method: POST

> ```text
> /api/v0/pin/add?arg=String&progress=Boolean
> ```
>
> #### Query Params

| Param | value |
| :--- | :--- |
| arg | String |
| progress | Boolean |

⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

### End-point: /object/stat

#### Description: Get stats for the DAG node named by .

Method: POST

> ```text
> /api/v0/object/stat?arg=String&human=Boolean
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
> /api/v0/object/put?inputenc=String&datafieldenc=String&pin=Boolean&quiet=Boolean
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
> /api/v0/object/get?arg=String&data-encoding=String
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
> /api/v0/object/data?arg=String
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
> /api/v0/dag/resolve?arg=String
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
> /api/v0/dag/put?format=String&input-enc=String&pin=Boolean&hash=String
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
> /api/v0/dag/get?arg=String
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
> /api/v0/cat?arg=String&offset=Int64&length=Int64
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
> /api/v0/block/stat?arg=String
> ```
>
> #### Query Params

| Param | value |
| :--- | :--- |
| arg | String |

⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃









