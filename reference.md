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

