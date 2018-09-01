# Pokémon

{% api-method method="get" host="https://pokeapi.bastionbot.org" path="/v1/pokemon/:name" %}
{% api-method-summary %}
Pokémon by name
{% endapi-method-summary %}

{% api-method-description %}
This endpoint returns an array of Pokémon objects containing all the forms of the Pokémon specified by the Pokémon name.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="name" type="string" required=true %}
The name of the Pokémon
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
Pokémon successfully retrived.
{% endapi-method-response-example-description %}

```javascript
[
    {
        "number": "25",
        "name": "Pikachu",
        "species": "Mouse",
        "types": [
            "Electric"
        ],
        "abilities": {
            "normal": [
                "Static"
            ],
            "hidden": [
                "Lightning Rod"
            ]
        },
        "eggGroups": [
            "Field",
            "Fairy"
        ],
        "gender": [
            50,
            50
        ],
        "height": "1'04\"",
        "weight": "13.2 lbs.",
        "family": {
            "id": 10,
            "evolutionStage": 2,
            "evolutionLine": [
                "Pichu",
                "Pikachu",
                "Raichu"
            ]
        },
        "starter": false,
        "legendary": false,
        "mythical": false,
        "ultraBeast": false,
        "mega": false,
        "gen": 1,
        "sprite": "https://pokeres.bastionbot.org/images/pokemon/25.png"
    }
]
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

#### Pokémon Structure

| Field | Type | Description |
| :--- | :--- | :--- |
| number | integer | The national Pokédex number of the Pokémon |
| name | string | The name of the Pokémon |
| species | string | The species the Pokémon belongs to |
| types | array of [Pokémon types](types.md) | The type of the Pokémon |
| abilities | array of normal and hidden Pokémon abilities | The abilities of the Pokémon |
| eggGroups | array of [Pokémon egg groups](egg-groups.md) | The egg groups the Pokémon belong to |
| height | string | The height of the Pokémon in feets |
| weight | string | The weight of the Pokémon in pounds |
| family | Pokémon family object | The family id, evolution stage and evolution line of the Pokémon |
| starter | bool | Is it a starter Pokémon |
| legendary | bool | Is it a legendary Pokémon |
| mythical | bool | Is it a mythical Pokémon |
| ultraBeast | bool | Is it an ultra beast |
| mega | bool | Is it a mega evolved form of the Pokémon |
| gen | integer | The generation the Pokémon was first discovered |
| sprite | string | The URL of an image of the Pokémon |

#### Example Request

```bash
curl -i -X GET \
  -H "User-Agent: BastionDiscordBot (https://bastionbot.org, v6.16.1)" \
  https://pokeapi.bastionbot.org/v1/pokemon/pikachu
```

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

####  Pokémon Counts Structure

| Field | Type | Description |
| :--- | :--- | :--- |
| gen1 | integer | The number of Pokémon discovered in this generation. |
| gen2 | integer | The number of Pokémon discovered in this generation. |
| ⋮ | ⋮ | ⋮ |
| total | integer | The total number of Pokémon discovered in the Pokémon World. |

#### Example Request

```bash
curl -i -X GET -H \
  "User-Agent: BastionDiscordBot (https://bastionbot.oorg, v6.16.1)" \
  https://pokeapi.bastionbot.org/v1/pokemon/counts
```

