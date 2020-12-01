# Rate limits

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

