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

{% api-method method="get" host="https://pokeapi.bastionbot.org" path="/v1/league/:slug" %}
{% api-method-summary %}
Get Pokémon League
{% endapi-method-summary %}

{% api-method-description %}
This endpoint returns a Pokémon League object containing the details about the league.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="slug" type="string" required=false %}
The string used to identify a region
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}

{% api-method-headers %}
{% api-method-parameter name="User-Agent" type="string" required=false %}
The User-Agent of your application
{% endapi-method-parameter %}
{% endapi-method-headers %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
League successfully retrieved
{% endapi-method-response-example-description %}

```javascript
{
    "name": "Kalos League",
    "slug": "kalos",
    "region": "Kalos",
    "badgesRequired": 8,
    "badges": [
        "Bug Badge",
        "Cliff Badge",
        "Rumble Badge",
        "Plant Badge",
        "Voltage Badge",
        "Fairy Badge",
        "Psychic Badge",
        "Iceberg Badge"
    ]
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

#### League Structure

| Field | Type | Description |
| :--- | :--- | :--- |
| name | string | The name of Pokémon league |
| slug | string | The string used to identify this region. |
| region | string | The region in the Pokémon World where the league happens |
| badgesRequired | integer | The minimum number of Pokémon gym badges required to qualify for the Pokémon league |
| badges | array of strings | The Pokémon gym badges that are eligible for the Pokémon league |

#### Example Request

```bash
curl -i -X GET -H \
  "User-Agent: BastionDiscordBot (https://bastionbot.oorg, v6.16.1)" \
  https://pokeapi.bastionbot.org/v1/league/kalos
```

