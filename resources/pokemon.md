# Pokémon

{% swagger baseUrl="https://ex.traction.one/pokedex" path="/pokemon/:slug" method="get" summary="Get Pokémon" %}
{% swagger-description %}
This endpoint returns an array of Pokémon objects containing all the forms of the Pokémon specified by the Pokémon name or number.
{% endswagger-description %}

{% swagger-parameter name="slug" type="string" required="true" in="path" %}
Either the name or the national Pokédex number of the Pokémon
{% endswagger-parameter %}

{% swagger-parameter name="User-Agent" type="string" required="false" in="header" %}
The User-Agent of your application
{% endswagger-parameter %}

{% swagger-response status="200" description="" %}
```json
[
  {
    "number": 658,
    "name": "Greninja",
    "gen": 6,
    "species": "Ninja Pokémon",
    "types": [
      "Water",
      "Dark"
    ],
    "abilities": [
      {
        "name": "Torrent",
        "description": "Powers up Water-type moves in a pinch.",
        "hidden": false
      },
      {
        "name": "Protean",
        "description": "Changes the Pokémon's type to its last used move.",
        "hidden": true
      }
    ],
    "height": "1.5 m (4′11″)",
    "weight": "40.0 kg (88.2 lbs)",
    "mega": false,
    "baseStats": {
      "hp": 72,
      "attack": 95,
      "defense": 67,
      "spAtk": 103,
      "spDef": 71,
      "speed": 122
    },
    "training": {
      "evYield": "3 Speed",
      "catchRate": "45 (5.9% with PokéBall, full HP)",
      "baseFriendship": "50 (normal)",
      "baseExp": "265",
      "growthRate": "Medium Slow"
    },
    "breeding": {
      "gender": "87.5% male, 12.5% female",
      "eggGroups": [
        "Water 1"
      ],
      "eggCycles": "20 (4,884–5,140 steps)"
    },
    "sprite": "https://img.pokemondb.net/sprites/home/normal/greninja.png"
  },
  {
    "number": 658,
    "name": "Ash-Greninja",
    "gen": 6,
    "species": "Ninja Pokémon",
    "types": [
      "Water",
      "Dark"
    ],
    "abilities": [
      {
        "name": "Battle Bond",
        "description": "Transform into Ash-Greninja after causing opponent to faint.",
        "hidden": false
      }
    ],
    "height": "1.5 m (4′11″)",
    "weight": "40.0 kg (88.2 lbs)",
    "mega": false,
    "baseStats": {
      "hp": 72,
      "attack": 145,
      "defense": 67,
      "spAtk": 153,
      "spDef": 71,
      "speed": 132
    },
    "training": {
      "evYield": "3 Speed",
      "catchRate": "45 (5.9% with PokéBall, full HP)",
      "baseFriendship": "50 (normal)",
      "baseExp": "265",
      "growthRate": "Medium Slow"
    },
    "breeding": {
      "gender": "100% male, 0% female",
      "eggGroups": [
        "Undiscovered"
      ],
      "eggCycles": "20 (4,884–5,140 steps)"
    },
    "sprite": "https://img.pokemondb.net/sprites/home/normal/greninja-ash.png"
  }
]
```
{% endswagger-response %}
{% endswagger %}

**Example Request**

```bash
curl -i -X GET \
  -H "User-Agent: BastionDiscordBot (https://bastion.traction.one, v10.13.0)" \
  https://ex.traction.one/pokedex/pokemon/greninja
```

```bash
curl -i -X GET \
  -H "User-Agent: BastionDiscordBot (https://bastion.traction.one, v10.13.0)" \
  https://ex.traction.one/pokedex/pokemon/658
```

{% swagger baseUrl="https://ex.traction.one/pokedex" method="get" path="/pokemon" summary="List Pokémon" %}
{% swagger-description %}
This endpoint returns an object with all the national Pokédex number mapped to the name of the Pokémon.
{% endswagger-description %}

{% swagger-parameter name="User-Agent" type="string" required="false" in="header" %}
The User-Agent of your application
{% endswagger-parameter %}

{% swagger-response status="200" description="" %}
```json
{
  "1": "Bulbasaur",
  "2": "Ivysaur",
  "3":"Venusaur",
  ...
  "1008": "Miraidon",
  "1009": "Walking Wake",
  "1010": "Iron Leaves"
}
```
{% endswagger-response %}
{% endswagger %}

**Example Request**

```bash
curl -i -X GET \
  -H "User-Agent: BastionDiscordBot (https://bastion.traction.one, v10.13.0)" \
  https://ex.traction.one/pokedex/pokemon
```
