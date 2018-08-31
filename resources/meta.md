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



