# Token APIs

### API Key Authentication

The Token APIs are secured by generated APP credentials and JWT Bearer Tokens:

* Scoped to a single App acting on behalf of a single Organization
* Revoked immediately by deleting the App

### Generating APP credentials

Use the developer console to create a new APP profile, or delete/revoke an existing App. Navigate to "Apps", then click "+ New Application"

![](../.gitbook/assets/testbed-create-app.png)

### Generating a JWT Bearer Token

JWT Bearer Token authenticates requests on behalf of your developer App.

This authentication method requires for you to pass a Bearer Token with your request, which you can generate within the Keys section of your developer Apps.

To use this authentication method, you'll need a bearer token, which you can generate by passing your app key and secret through the POST auth/token endpoint.

```bash
curl --request POST \
--url 'https://api.token-project.eu/auth/token?key=LJHyxcBqWKLhZdxZo9X5yBFvJQpWYfCT&secret=vbQ6esJgef9ktKymZ9HKKmMaHZCLRmGN'
```

As a result you'll receive a response similar to this:

```javascript
{
    "token_type": "bearer",
    "access_token": "eyJhbGciOiJSUzI1N324rR5cCI6IkpXVCJ9.eyJzdWIiOiJMSkh5eGNCcVdLTGhaZHhabzlYNXlCRnZKUXBXWWZDVCIsIm93bmVyIjp7InVpZCI6ImJCWjd4bkFOakNEM21oY1cyIiwidW5hbWUiOiJ4dXJ4byIsInVhdmF0YXIiOiIvL3d3dy5ncmF2YXRhci5jb20vYXZhdGFyLzQzNTcyYzRmNWNkMmY0NTMyYTdjNjdjZDUyOWNlYjRiP2Q9aWRlbnRpY29uIn0sImFwcF9uYW1lIjoiTXkgQXBwIiwic2NvcGUiOlsibm90YXJpemF0aW9uOioiLCJzdG9yYWdlOioiLCJpcGZzOioiLCJzdHJlYW1zOioiLCJjb25uZWN0OioiLCJpbmZ1cmE6KiIsImNsdXN0ZXI6KiIsInNzbyJdLCJhdWQiOiJodHRwczovL2RldmVsb3BlcnMudG9rZW4tcHJvamVjdC5ldSIsImdyYW50X3R5cGUiOiJjbGllbnRfY3JlZGVudGlhbHMiLCJpYXQiOjE2MDY3ODcyMjh9.cFQlf9xHbYh_YQ5mQE9qMnsw9thJhiL4trmf2OsFtMjkYf_nXjWvYp0P_zcq5y0FqOryU2x8549T5uqsEiy4ookhxUBCDQFKdzYWwMzg_1F47e6P9Mh_HULaWQO-L7RYG3neiSpta8NtlUxiqeW0Ml7JwWy7ANMHWulgFXsLLb8tC0KNcOL7nnHO_wc1qI3svyD2tX1KEMBnqpezgmBBe0Za7Fwk07NL4_DvbXPpdxlvKmGCBiPuCVhm13JxSSy_EO4QgedvpEabYNvI7LEJWik0gby4k_SodwB_w_QQ_vKhbzEX2TktJy3QMHmkDIYIaHOuR9SjeUaioK_SSaS_ew"
}
```

Once you have your JWT Bearer Token you can start interacting with any of the Token APIs.

When making an API call, supply the JWT as a Bearer token in the Authorization header:

Here is an example of what a API request looks like. You must replace $BEARER\_TOKEN with the Bearer Token that you generate in the previous step, and have the proper access for this request to work:

```bash
curl --request GET \
  --url 'https://api.token-project.eu/notarizations/stamps' \
  --header 'authorization: Bearer $BEARER_TOKEN'
```

API calls using JWT Bearer Token are rate limited per endpoint at the App-level.

### Debuging a JWT Bearer Token

```javascript
  "sub": "LJHyxcBqWKLhZdxZo9X5yBFvJQpWYfCT",
  "owner": {
    "uid": "bBZ7xnANjCD3mhcW2",
    "uname": "xurxo",
    "uavatar": "//www.gravatar.com/avatar/43572c4f5cd2f4532a7c67cd529ceb4b?d=identicon"
  },
  "app_name": "My App",
  "scope": [
    "notarization:*",
    "storage:*",
    "ipfs:*",
    "streams:*",
    "connect:*",
    "infura:*",
    "cluster:*",
    "sso"
  ],
  "aud": "https://developers.token-project.eu",
  "grant_type": "client_credentials",
  "iat": 1606787228
}
```

### Rate limits

To help manage the volume of API requests, all API calls are rate limited per endpoint at the App-level. 

The maximum number of requests that are allowed is based on a time interval, some specified period or window of time. The most common request limit is 10 requests for a two minutes interval. If an endpoint has a rate limit of 10 requests/2-minutes, then up to 10 requests over any 2-minute interval is allowed.

Rate limits are determined by the number of requests you make using a Bearer Token. If an endpoint allows for 10 requests per rate limit window, then you can make 10 requests per window on behalf of your App by passing a Bearer Token.

### HTTP headers and response codes

Use the HTTP headers in order to understand where the application is at for a given rate limit, on the method that was just utilized.

Note that the HTTP headers are contextual, they indicate the rate limit for the application context.

```text
X-RateLimit-Limit: the rate limit ceiling for that given endpoint
X-RateLimit-Remaining: the number of requests left for the 15-minute window
X-RateLimit-Reset: the remaining window before the rate limit resets, in UTC epoch seconds
```

When an application exceeds the rate limit for a given endpoint, the API will return a HTTP 429 “Too Many Requests” response code, and the following error will be returned in the response body:

```javascript
{ "errors": [ { "code": 88, "message": "Rate limit exceeded" } ] }
```

### Recovering from a rate limit 429 errors

When these rate limits are exceeded, a 429 'Too many requests' error is returned from the endpoint.

As discussed below, when rate limit errors occur, a best practice is to examine HTTP headers that indicate when the limit resets and pause requests until then.

When a "too many requests" or rate-limiting error occurs, the frequency of making requests needs to be slowed down. When a rate limit error is hit, the x-rate-limit-reset: HTTP header can be checked to learn when the rate-limiting will reset.

