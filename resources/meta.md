# Meta

{% api-method method="get" host="https://pokeapi.bastionbot.org" path="/info" %}
{% api-method-summary %}
Get API Information
{% endapi-method-summary %}

{% api-method-description %}
This endpoint returns basic information about the Pokédex API.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="User-Agent" type="string" required=false %}
The User-Agent for your application
{% endapi-method-parameter %}
{% endapi-method-headers %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Information successfully retrieved.
{% endapi-method-response-example-description %}

```javascript
{
    "title": "Pokédex API",
    "baseURL": "https://pokeapi.bastionbot.org",
    "resourceURL": "https://pokeres.bastionbot.org",
    "versions": [
        "/v1"
    ],
    "author": "Sankarsan Kampa"
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

#### Info Structure

| Field | Type | Description |
| :--- | :--- | :--- |
| title | string | The name the API |
| baseURL | string | The base URL of the API for requesting resources |
| resourceURL | string | The base URL of the image and other resources required by the API |
| versions | array of strings | Available versions of the API |
| author | string | The author/developer of the API |

#### Example Request

```bash
curl -i -X GET \
  -H "User-Agent: BastionDiscordBot (https://bastionbot.org, v6.16.1)" \
  https://pokeapi.bastionbot.org/info
```

{% api-method method="get" host="https://pokeapi.bastionbot.org" path="/stats" %}
{% api-method-summary %}
Get API Statistics
{% endapi-method-summary %}

{% api-method-description %}
This endpoint returns basic statistics of the Pokédex API.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="User-Agent" type="string" required=false %}
The User-Agent for your application
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```javascript
{
    "total_hits": "1337",
    "session_hits": "201",
    "uptime": 658
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

#### Stats Structure

| Field | Type | Description |
| :--- | :--- | :--- |
|  total\_hits | string | Total number of API calls made to Pokédex API |
|  session\_hits | string | Number of API calls made to Pokédex API since last restart |
| uptime | number | Number of seconds elapsed since Pokédex API server was booted |

#### Example Request

```bash
curl -i -X GET \
  -H "User-Agent: BastionDiscordBot (https://bastionbot.org, v6.16.1)" \
  https://pokeapi.bastionbot.org/stats
```

