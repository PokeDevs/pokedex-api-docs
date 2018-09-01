# Pokémon

{% api-method method="get" host="https://pokeapi.bastionbot.org" path="/v1/pokemon/counts" %}
{% api-method-summary %}
Pokémon Counts
{% endapi-method-summary %}

{% api-method-description %}
This endpoint returns a Pokémon Counts object containing the number of Pokémon in each generation and the total number of Pokémon in the Pokémon World.
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
Counts successfully retrieved.
{% endapi-method-response-example-description %}

```javascript
{
    "gen1": 151,
    "gen2": 100,
    "gen3": 135,
    "gen4": 107,
    "gen5": 156,
    "gen6": 72,
    "gen7": 86,
    "total": 807
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

