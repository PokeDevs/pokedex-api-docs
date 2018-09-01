# Evolution Stones

{% api-method method="get" host="https://pokeapi.bastionbot.org" path="/v1/evolution-stone" %}
{% api-method-summary %}
Get Evolution Stone Names
{% endapi-method-summary %}

{% api-method-description %}
This endpoint returns an array of Pokémon Evolution Stone names discovered in the Pokémon World.
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
Evolution stone names successfully retrieved.
{% endapi-method-response-example-description %}

```javascript
[
    "Fire Stone",
    "Water Stone",
    "Thunder Stone",
    "Leaf Stone",
    "Moon Stone",
    "Sun Stone",
    "Shiny Stone",
    "Dusk Stone",
    "Dawn Stone",
    "Ice Stone"
]
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

#### Example Request

```bash
curl -i -X GET \
  -H "User-Agent: BastionDiscordBot (https://bastionbot.org, v6.16.1po)" \
  https://pokeapi.bastionbot.org/v1/evolution-stone
```

