# Leagues

{% api-method method="get" host="https://pokeapi.bastionbot.org" path="/v1/league" %}
{% api-method-summary %}
Get Pokémon League Names
{% endapi-method-summary %}

{% api-method-description %}
This endpoint returns an array of Pokémon League names known to us.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="User-Agent" type="string" required=false %}
The User-Agent of your application
{% endapi-method-parameter %}
{% endapi-method-headers %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
League names successfully retrieved.
{% endapi-method-response-example-description %}

```javascript
[
    "Indigo League",
    "Johto League",
    "Hoenn League",
    "Sinnoh League",
    "Unova League",
    "Kalos League",
    "Orange League"
]
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

#### Example Request

```bash
curl -i -X GET \
  -H "User-Agent: BastionDiscordBot (https://bastionbot.org, v6.16.1)" \
  https://pokeapi.bastionbot.org/v1/league
```

