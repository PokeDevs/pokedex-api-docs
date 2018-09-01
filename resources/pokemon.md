# Pokémon

{% api-method method="get" host="https://pokeapi.bastionbot.org" path="/v1/pokemon/:slug" %}
{% api-method-summary %}
Pokémon
{% endapi-method-summary %}

{% api-method-description %}
This endpoint returns an array of Pokémon objects containing all the forms of the Pokémon specified by the Pokémon name.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="slug" type="string" required=true %}
Either the name or the national Pokédex number of the Pokémon
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
    "number": "658",
    "name": "Greninja",
    "species": "Ninja",
    "types": [
      "Water",
      "Dark"
    ],
    "abilities": {
      "normal": [
        "Torrent"
      ],
      "hidden": [
        "Protean"
      ]
    },
    "eggGroups": [
      "Water 1"
    ],
    "gender": [
      87.5,
      12.5
    ],
    "height": "4'11\"",
    "weight": "88.2 lbs.",
    "family": {
      "id": 331,
      "evolutionStage": 3,
      "evolution-line": [
        "Froakie",
        "Frogadier",
        "Greninja"
      ]
    },
    "starter": false,
    "legendary": false,
    "mythical": false,
    "ultraBeast": false,
    "mega": false,
    "gen": 6,
    "sprite": "https://pokeres.bastionbot.org/images/pokemon/658.png"
  },
  {
    "number": "658",
    "name": "Ash-Greninja",
    "species": "Ninja",
    "types": [
      "Water",
      "Dark"
    ],
    "abilities": {
      "normal": [
        "Torrent"
      ],
      "hidden": [
        "Battle Bond"
      ]
    },
    "eggGroups": [
      "Water 1"
    ],
    "gender": [
      87.5,
      12.5
    ],
    "height": "4'11\"",
    "weight": "88.2 lbs.",
    "family": {
      "id": 331,
      "evolutionStage": 3,
      "evolution-line": [
        "Froakie",
        "Frogadier",
        "Greninja"
      ]
    },
    "starter": false,
    "legendary": false,
    "mythical": false,
    "ultraBeast": false,
    "mega": false,
    "gen": 6,
    "sprite": "https://pokeres.bastionbot.org/images/pokemon/658-ash.png"
  }
]
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=404 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```javascript
{
  "error": 404,
  "message": "Oh snap! No Pokémon has been discovered in this region. You should head home: https://pokedevs.bastionbot.org"
}
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
| family | [Pokémon family object](pokemon.md#pokemon-family-structure) | The family id, evolution stage and evolution line of the Pokémon |
| starter | bool | Is it a starter Pokémon |
| legendary | bool | Is it a legendary Pokémon |
| mythical | bool | Is it a mythical Pokémon |
| ultraBeast | bool | Is it an ultra beast |
| mega | bool | Is it a mega evolved form of the Pokémon |
| gen | integer | The generation the Pokémon was first discovered |
| sprite | string | The URL of an image of the Pokémon |

#### Pokémon Family Structure

| Field | Type | Description |
| :--- | :--- | :--- |
| id | integer | The id of Pokémon family |
| evolutionStage | integer | The evolved stage of the Pokémon in its evolution line |
| evolutionLine | array of strings | The list of Pokémon in its evolution line, in order |

#### Example Request

```bash
curl -i -X GET \
  -H "User-Agent: BastionDiscordBot (https://bastionbot.org, v6.16.1)" \
  https://pokeapi.bastionbot.org/v1/pokemon/greninja
```

```bash
curl -i -X GET \
  -H "User-Agent: BastionDiscordBot (https://bastionbot.org, v6.16.1)" \
  https://pokeapi.bastionbot.org/v1/pokemon/658
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

