# Authentication

The Token APIs are secured by generated APP credentials and JWT Bearer Tokens:

* Scoped to a single App acting on behalf of a single Organization
* Revoked immediately by deleting the App

### Generating APP credentials

Use the [developer portal](https://developers.token-project.eu) to create a new App profile, or delete/revoke an existing App. Navigate to "[Applications](https://developers.token-project.eu/apps)", then click "+ New Application"

![](<../.gitbook/assets/testbed-create-app (1) (1).png>)

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

API calls using JWT Bearer Token are [rate limited](rate-limits.md) per endpoint at the App-level.

### Debugging a JWT Bearer Token

To see detailed info for an access token go to the [Developer Portal](https://developers.token-project.eu)->[Developer tools](https://developers.token-project.eu/tools/)->[Access token debugger](https://developers.token-project.eu/tools/debugger) and enter your JWT Token.

If the token is valid you'll receive a response similar to this:

```javascript
{
  "sub": "LJHyxcBqWKLhZdxZo9X5yBFvJQpWYfCT",
  "owner": {
    "uid": "bBZ7xnA343dcW2",
    "uname": "username",
    "uavatar": "//www.gravatar.com/avatar/43572c4f5cd2f4532a7c67cd529ceb4b?d=identicon"
  },
  "app_name": "My App",
  "scope": [
    "notarization:*",
    "storage:*",
    "ipfs:*",
    "streams:*",
    "connect:*"
  ],
  "aud": "https://developers.token-project.eu",
  "grant_type": "client_credentials",
  "iat": 1606787228
}
```
