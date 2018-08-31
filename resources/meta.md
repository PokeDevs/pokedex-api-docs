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
The User-Agent for your application/library.
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

