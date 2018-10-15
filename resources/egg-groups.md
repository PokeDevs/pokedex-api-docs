# Egg Groups

{% api-method method="get" host="https://pokeapi.glitch.me" path="/v1/egg-groups" %}
{% api-method-summary %}
Pokémon Egg Groups
{% endapi-method-summary %}

{% api-method-description %}
This endpoint returns an array of Pokémon Egg Groups discovered in the Pokémon World.
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
Egg groups successfully retrieved.
{% endapi-method-response-example-description %}

```javascript
[
    "Bug",
    "Ditto",
    "Dragon",
    "Fairy",
    "Field",
    "Flying",
    "Grass",
    "Gender unknown",
    "Human-Like",
    "Mineral",
    "Monster",
    "Amorphous",
    "Undiscovered",
    "Water 1",
    "Water 2",
    "Water 3"
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
  https://pokeapi.glitch.me/v1/egg-groups
```

