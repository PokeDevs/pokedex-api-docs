# Reference

### API Reference {#api-reference}

Pokédex API is based on a single layer, a HTTPS/REST consumption-only API that only allows the `GET` method to consume all the Pokémon information you’ll ever need.

### Base URL {#base-url}

The base URL for all API requests is:

```text
https://pokeapi.bastionbot.org
```

### API Versioning {#api-versioning}

Pokédex API exposes different versions of the API. You can specify version by including it in the request path:

```text
https://pokeapi.bastionbot.org/v{version_number}
```

Omitting the version number from the route will route requests to the current default version. We recommend specifying a version number in the request path so that your app doesn’t run into incompatibility when the default version is changed.V

| Version | Status | Default |
| :--- | :--- | :--- |
| 1 | Available | ✔ |

### Authentication {#authentication}

No authentication is required to access this API. All the resources are and available to everyone. However, we will implement authentication methods in the future that will give authenticated users higher rate limits or no rate limits at all \(more on [rate limits](reference.md#rate-limiting) later\).

### User Agent {#user-agent}

Applications and websites using the API must provide a valid [User Agent](https://www.w3.org/Protocols/rfc2616/rfc2616-sec14.html#sec14.43) which specifies information about the app and website, in the following format:

```http
User-Agent: AppName ($url, $version)
```

Applications and websites may append more information and metadata to the end of this string as they wish.

#### Example User Agent Header {#example-user-agent-header}

```http
User-Agent: BastionDiscordBot (https://bastionbot.org, 6.16.1)
```

### Rate Limiting {#rate-limiting}

This API implements a process for limiting and preventing excessive requests in accordance with [RFC 6585](https://tools.ietf.org/html/rfc6585#section-4).

This API rate limits requests in order to prevent abuse and overload of our services. Rate limits are applied on a global basis, spanning across the entire API.

Because we may change rate limits at any time and rate limits can be different per application, rate limits should not be hard coded into your application or website. In order to properly support our dynamic rate limits, your application or website should parse for our rate limits in response headers and locally prevent exceeding of the limits as they change.

{% hint style="info" %}
Current rate limit is 500 API calls in 12 hours. And we will increase the rate limits every time we upgrade our server for better performance.
{% endhint %}

We recommend that your application or website should locally cache the data that you receive to save the number of API calls consumed for the same resource.

#### Header Format {#header-format}

For every API request made, we return optional HTTP response headers containing the rate limit encountered during your request.

```http
Retry-After: 1301000
X-RateLimit-Limit: 500
X-RateLimit-Remaining: 201
X-RateLimit-Reset: 905212800000
```

`Retry-After` - The number of milliseconds after which the rate limit will reset. It is returned only if you’ve been rate limited.

`X-RateLimit-Limit` - The number of requests that can be made

`X-RateLimit-Remaining` - The number of remaining requests that can be made

`X-RateLimit-Reset` - Epoch time \(seconds since 00:00:00 UTC on January 1, 1970\) at which the rate limit resets. It is returned only if you’ve been rate limited.

#### Exceeding A Rate Limit {#exceeding-a-rate-limit}

In the case that a rate limit is exceeded, the API will return a HTTP 429 response code with a JSON body.

| Field | Type | Description |
| :--- | :--- | :--- |
| error | integer |  The HTTP response code. |
| message | string |  A message saying you are being rate limited. |
| retry\_after | integer |  The number of milliseconds to wait before submitting another request. |

Note that the normal rate-limiting headers will be sent in this response.

{% hint style="warning" %}
API users that regularly hit and ignore rate limits will be banned \(by their IP address\) from using the API again.
{% endhint %}

#### Example Rate Limit Response {#example-rate-limit-response}

The rate-limiting response will look something like the following:

```bash
< HTTP/1.1 429 TOO MANY REQUESTS
< Content-Type: application/json
< Retry-After: 14400000
< X-RateLimit-Limit: 500
< X-RateLimit-Remaining: 0
< X-RateLimit-Reset: 905212800000
{
  "error": 429,
  "message": "You are being rate limited. You're way too spicy at catching Pokémon.",
  "retry_after": 14400000
}
```

