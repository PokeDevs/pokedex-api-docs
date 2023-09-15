# Evolution Stones

{% swagger baseUrl="https://ex.traction.one/pokedex" path="/evolution/stones" method="get" summary="List Evolution Stone" %}
{% swagger-description %}
This endpoint returns an array of Pokémon Evolution Stone names discovered in the Pokémon World.
{% endswagger-description %}

{% swagger-parameter in="header" name="User-Agent" type="string" %}
The User-Agent of your application
{% endswagger-parameter %}

{% swagger-response status="200" description="Evolution stone names successfully retrieved." %}
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
{% endswagger-response %}
{% endswagger %}

**Example Request**

```bash
curl -i -X GET \
  -H "User-Agent: BastionDiscordBot (https://bastion.traction.one, v10.13.0)" \
  https://ex.traction.one/pokedex/evolution/stones
```

{% swagger baseUrl="https://ex.traction.one/pokedex" path="/evolution/stones/:slug" method="get" summary="Get Evolution Stone" %}
{% swagger-description %}
This endpoint returns a Evolution Stone object containing the details about the evolution stone.
{% endswagger-description %}

{% swagger-parameter in="path" name="slug" type="string" %}
The string used to identify this evolution stone
{% endswagger-parameter %}

{% swagger-parameter in="header" name="User-Agent" type="string" %}
The User-Agent of your application
{% endswagger-parameter %}

{% swagger-response status="200" description="Evolution stone successfully retrieved." %}
```json
{
  "name": "Dusk Stone",
  "aka": "Darkness Stone",
  "slug": "dusk",
  "effects": [
    "Causes Murkrow to evolve into Honchkrow.",
    "Causes Misdreavus to evolve into Mismagius.",
    "Causes Lampent to evolve into Chandelure.",
    "Causes Doublade to evolve into Aegislash."
  ],
  "sprite": "https://archives.bulbagarden.net/media/upload/9/9d/Bag_Dusk_Stone_SV_Sprite.png"
}
```
{% endswagger-response %}
{% endswagger %}

**Example Request**

```bash
curl -i -X GET \
  -H "User-Agent: BastionDiscordBot (https://bastion.traction.one, v10.13.0)" \
  https://ex.traction.one/pokedex/evolution/stones/dusk
```
