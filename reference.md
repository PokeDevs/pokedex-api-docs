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

No authentication is required to access this API. All the resources are and available to everyone. However, we will implement authentication methods in the future that will give authenticated users higher rate limits or no rate limits at all \(more on rate limits later\).

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



