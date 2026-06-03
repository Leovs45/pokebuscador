# Pokébuscador

Proyecto rápido para explorar el consumo de APIs REST desde el front-end, sin frameworks ni build tools — HTML, CSS y JS vanilla en un solo archivo.

## Qué hace

- Busca cualquier pokémon por nombre o número y muestra su sprite, tipos y estadísticas base.
- Genera un "pokémon del día" único por usuario: cada visitante recibe un pokémon diferente que se mantiene fijo durante el día.

## Conceptos que cubre

**Consumo de API REST**
Usa [PokéAPI](https://pokeapi.co/), una API pública y sin autenticación. Cada búsqueda hace un `fetch` a `https://pokeapi.co/api/v2/pokemon/{nombre-o-id}` y trabaja con la respuesta JSON.

**Caché en localStorage**
Para no repetir llamadas innecesarias, cada respuesta de la API se guarda en `localStorage`. La segunda vez que buscás el mismo pokémon, no hay request — se lee directo del navegador.

**Identidad de usuario sin backend**
El pokémon del día se genera con un hash de la fecha + un seed aleatorio guardado en `localStorage`. Esto garantiza que cada persona vea un pokémon distinto pero que no cambie durante el día, sin ningún servidor ni cuenta de usuario.

## Stack

- HTML + CSS + JavaScript vanilla
- PokéAPI (REST, sin autenticación)
- localStorage para caché y persistencia
