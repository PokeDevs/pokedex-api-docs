# Reference

## API Reference <a href="#api-reference" id="api-reference"></a>

Pokédex API is based on a single layer, a HTTPS/REST consumption-only API that only allows the `GET` method to consume all the Pokémon information you’ll ever need.

## Base URL <a href="#base-url" id="base-url"></a>

The base URL for all API requests is:

```
https://ex.traction.one/pokedex
```

## Authentication <a href="#authentication" id="authentication"></a>

No authentication is required to access this API. All the resources are and available to everyone. However, we will implement authentication methods in the future that will give authenticated users higher rate limits or no rate limits at all (more on [rate limits](reference.md#rate-limiting) later).

## User Agent <a href="#user-agent" id="user-agent"></a>

Applications and websites using the API must provide a valid [User Agent](https://www.w3.org/Protocols/rfc2616/rfc2616-sec14.html#sec14.43) which specifies information about the app and website, in the following format:

```http
User-Agent: AppName ($url, $version)
```

Applications and websites may append more information and metadata to the end of this string as they wish.

### Example User Agent Header <a href="#example-user-agent-header" id="example-user-agent-header"></a>

```http
User-Agent: BastionDiscordBot (https://bastion.traction.one, v10.12)
```

## Rate Limiting <a href="#rate-limiting" id="rate-limiting"></a>

This API implements a process for limiting and preventing excessive requests in accordance with [RFC 6585](https://tools.ietf.org/html/rfc6585#section-4).

This API rate limits requests in order to prevent abuse and overload of our services. Rate limits are applied on a global basis, spanning across the entire API.

Because we may change rate limits at any time and rate limits can be different per application, rate limits should not be hard coded into your application or website. In order to properly support our dynamic rate limits, your application or website should parse for our rate limits in response headers and locally prevent exceeding of the limits as they change.

{% hint style="info" %}
Current rate limit is 50 API calls in 10 minutes. And we will increase the rate limits every time we upgrade our server for better performance.
{% endhint %}

We recommend that your application or website should locally cache the data that you receive to save the number of API calls consumed for the same resource.

### Header Format <a href="#header-format" id="header-format"></a>

For every API request made, we return optional HTTP response headers containing the rate limit encountered during your request.

```http
Retry-After: 1301000
RateLimit-Limit: 500
RateLimit-Remaining: 201
RateLimit-Reset: 905212800000
```

`Retry-After` - The number of milliseconds after which the rate limit will reset. It is returned only if you’ve been rate limited.

`RateLimit-Limit` - The number of requests that can be made

`RateLimit-Remaining` - The number of remaining requests that can be made

`RateLimit-Reset` - Epoch time (seconds since 00:00:00 UTC on January 1, 1970) at which the rate limit resets. It is returned only if you’ve been rate limited.

### Exceeding A Rate Limit <a href="#exceeding-a-rate-limit" id="exceeding-a-rate-limit"></a>

In the case that a rate limit is exceeded, the API will return a HTTP 429 response code with a JSON body.

| Field   | Type    | Description                                  |
| ------- | ------- | -------------------------------------------- |
| status  | integer | The HTTP response code.                      |
| message | string  | A message saying you are being rate limited. |

Note that the normal rate-limiting headers will be sent in this response.

{% hint style="warning" %}
API users that regularly hit and ignore rate limits will be banned (by their IP address) from using the API again.
{% endhint %}

### Example Rate Limit Response <a href="#example-rate-limit-response" id="example-rate-limit-response"></a>

The rate-limiting response will look something like the following:

```bash
< HTTP/1.1 429 TOO MANY REQUESTS
< Content-Type: application/json
< Retry-After: 14400000
< RateLimit-Limit: 500
< RateLimit-Remaining: 0
< RateLimit-Reset: 905212800000
{
  "error": 429,
  "message": "Too many requests, please try again later."
}
```
