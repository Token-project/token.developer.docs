# TokenServices

## Project: Token Services

## 📁 Collection: Auth

### End-point: Debug token

#### Description: resr

Method: GET

> ```text
>
> ```

⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

### End-point: Get user granted permissions

#### Description: resr

Method: GET

> ```text
>
> ```

⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

### End-point: Identify user

#### Description: Checks authentication & identity

This method checks authentication and tells "you" who you are.

You can also use this method to test whether FundingBox API authentication is functional. Method: GET

> ```text
>
> ```

⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

### End-point: Refresh token

#### Description: resr

Method: GET

> ```text
>
> ```

⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

### End-point: GET authorization token

#### Description: resr

Method: POST

> ```text
> https://auth.fundingbox.com/token
> ```

⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## 📁 Collection: Notarization

### End-point: Stamping a hash

#### Description: Creates a timestamp for a given SHA-256 hash hexadecimal digest. Please note that POST requests must include the Content-Type: application/json header.

The response is JSON-encoded object containing the ID and the time of the stamp. The receipt object gives an estimated time in seconds for the different receipt types \(ethereum and bitcoin\) to be ready for retrieval. Method: POST

> ```text
> http://api.ledgerproject.eu/stamp
> ```
>
> #### Headers

| Content-Type | Value |
| :--- | :--- |
| Content-Type | application/x-www-form-urlencoded |

#### 🔑 Authentication bearer

| Param | value | Type |
| :--- | :--- | :--- |
| token | eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJleHAiOjE1NTAwMzM1NzksInVzZXJuYW1lIjoiam9yZ2U3NzMiLCJvcmdOYW1lIjoiT3JnMSIsImlhdCI6MTU0OTk5NzU3OX0.JZOoLBO5Jq5ed-2PUYctboVdxcLVm3kdGdpdAhTcADU | string |

⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

### End-point: SignUp

#### Description: Creates a timestamp for a given SHA-256 hash hexadecimal digest. Please note that POST requests must include the Content-Type: application/json header.

The response is JSON-encoded object containing the ID and the time of the stamp. The receipt object gives an estimated time in seconds for the different receipt types \(ethereum and bitcoin\) to be ready for retrieval. Method: POST

> ```text
> {{protocol}}://{{host}}:{{port}}/{{services.notarization}}/users
> ```
>
> #### Headers

| Content-Type | Value |
| :--- | :--- |
| Content-Type | application/x-www-form-urlencoded |

#### 🔑 Authentication noauth

| Param | value | Type |
| :--- | :--- | :--- |


⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

### End-point: Retrieving all stamps

#### Description: Retrieves all stamps made by the requesting client, ordered by date, from newest to oldest, paginated in chunks of 50.

You can add ?page=N at the end of the URL in order to show the Nth page. If N is not specified, it is assumed to be 0 and therefore the last 50 stamps are returned.

The response is a JSON-encoded object containing an array of stamps. If a certain receipt found inside a stamp is a number instead of an object, that number is the estimated number of seconds before the final receipt will be ready. Method: GET

> ```text
> {{protocol}}://{{host}}:{{port}}/{{services.notarization}}/stamps
> ```
>
> #### Headers

| Content-Type | Value |
| :--- | :--- |
| Content-Type | application/x-www-form-urlencoded |

⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

### End-point: blockinfos transactionID

#### Description: Retrieves all stamps made by the requesting client, ordered by date, from newest to oldest, paginated in chunks of 50.

You can add ?page=N at the end of the URL in order to show the Nth page. If N is not specified, it is assumed to be 0 and therefore the last 50 stamps are returned.

The response is a JSON-encoded object containing an array of stamps. If a certain receipt found inside a stamp is a number instead of an object, that number is the estimated number of seconds before the final receipt will be ready. Method: GET

> ```text
> {{protocol}}://{{host}}:{{port}}/{{services.notarization}}/blockinfos/transactions/582dfec2972af002022b1a84e0fe2605464846233f4c05edc4e91825f143b9c0
> ```
>
> #### Headers

| Content-Type | Value |
| :--- | :--- |
| Content-Type | application/x-www-form-urlencoded |

⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

### End-point: blockinfos blockHash

#### Description: Retrieves all stamps made by the requesting client, ordered by date, from newest to oldest, paginated in chunks of 50.

You can add ?page=N at the end of the URL in order to show the Nth page. If N is not specified, it is assumed to be 0 and therefore the last 50 stamps are returned.

The response is a JSON-encoded object containing an array of stamps. If a certain receipt found inside a stamp is a number instead of an object, that number is the estimated number of seconds before the final receipt will be ready. Method: GET

> ```text
> http://api.ledgerproject.eu/blockinfos/blocks/hash/48815dc12e627f5ccaea4106a9255a277a95b7c87d5a64d6fb04cc634ba8d4d3
> ```
>
> #### Headers

| Content-Type | Value |
| :--- | :--- |
| Content-Type | application/x-www-form-urlencoded |

⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

### End-point: blockinfos blockID

#### Description: Retrieves all stamps made by the requesting client, ordered by date, from newest to oldest, paginated in chunks of 50.

You can add ?page=N at the end of the URL in order to show the Nth page. If N is not specified, it is assumed to be 0 and therefore the last 50 stamps are returned.

The response is a JSON-encoded object containing an array of stamps. If a certain receipt found inside a stamp is a number instead of an object, that number is the estimated number of seconds before the final receipt will be ready. Method: GET

> ```text
> {{protocol}}://{{host}}:{{port}}/{{services.notarization}}/blockinfos/blocks/3
> ```
>
> #### Headers

| Content-Type | Value |
| :--- | :--- |
| Content-Type | application/x-www-form-urlencoded |

⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

### End-point: blockinfos

#### Description: Retrieves all stamps made by the requesting client, ordered by date, from newest to oldest, paginated in chunks of 50.

You can add ?page=N at the end of the URL in order to show the Nth page. If N is not specified, it is assumed to be 0 and therefore the last 50 stamps are returned.

The response is a JSON-encoded object containing an array of stamps. If a certain receipt found inside a stamp is a number instead of an object, that number is the estimated number of seconds before the final receipt will be ready. Method: GET

> ```text
> {{protocol}}://{{host}}:{{port}}/{{services.notarization}}/blockinfos/stamp/keys/blablabla
> ```
>
> #### Headers

| Content-Type | Value |
| :--- | :--- |
| Content-Type | application/x-www-form-urlencoded |

⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

### End-point: Retrieving receipts for a stamp

#### Description: Retrieves all receipts \(also known as proofs in former Stampery API versions\) for a certain stamp.

The response is a JSON-encoded object containing an array of stamps. If a certain receipt found inside a stamp is a number instead of an object, that number is the estimated number of seconds before the final receipt will be ready. Method: GET

> ```text
> {{protocol}}://{{host}}:{{port}}/{{services.notarization}}/stamp/2f3f3a85340bde09b505b0d37235d1d32a674e43a66229f9a205e7d8d5328ed1
> ```
>
> #### Headers

| Content-Type | Value |
| :--- | :--- |
| Content-Type | application/x-www-form-urlencoded |

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

## 📁 Collection: IPFS Cluster Peers Administration

