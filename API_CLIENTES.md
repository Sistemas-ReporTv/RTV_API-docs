---
title: "RTV API — Guía para clientes"
description: "La API permite consultar la última versión disponible de cada conjunto de datos RTV. Reemplazá `{processId}` por el identificador de proceso asignado a tu integración."
lang: es
translation_path: "API_CLIENTES.html"
---

# RTV API — Guía para clientes

La API permite consultar la última versión disponible de cada conjunto de datos
RTV. Reemplazá `{processId}` por el identificador de proceso asignado a tu
integración.

## Consulta

```http
GET /api/v1/rtv/processes/{processId}/latest/{resource}
```

Por defecto se devuelve la actualización más reciente. Para pedir la versión
generada para una fecha determinada, agregá el parámetro opcional `from`:

```http
GET /api/v1/rtv/processes/123/latest/programs?from=2026-08-03
```

La fecha utiliza el formato `AAAA-MM-DD`.

## Recursos disponibles

Cada recurso tiene una página con el formato de respuesta y la descripción de
los datos que expone.

| Recurso y documentación | Contenido |
|---|---|
| [`/latest/teams`](recursos/teams.md) | Equipos deportivos disponibles para el proceso. |
| [`/latest/tournaments`](recursos/tournaments.md) | Torneos y competencias deportivas disponibles. |
| [`/latest/stadiums`](recursos/stadiums.md) | Estadios y sedes deportivas disponibles. |
| [`/latest/awards`](recursos/awards.md) | Catálogo de premios disponible. |
| [`/latest/related-program-types`](recursos/related-program-types.md) | Tipos utilizados para relacionar programas entre sí. |
| [`/latest/channels`](recursos/channels.md) | Señales o canales incluidos en el proceso. |
| [`/latest/categories`](recursos/categories.md) | Categorías utilizadas para clasificar el contenido. |
| [`/latest/genres`](recursos/genres.md) | Géneros utilizados para clasificar el contenido. |
| [`/latest/subgenres`](recursos/subgenres.md) | Subgéneros utilizados para clasificar el contenido. |
| [`/latest/genre-subgenres`](recursos/genre-subgenres.md) | Asociaciones válidas entre géneros y subgéneros. |
| [`/latest/category-genres`](recursos/category-genres.md) | Asociaciones válidas entre categorías y géneros. |
| [`/latest/clients`](recursos/clients.md) | Clientes habilitados en el feed. |
| [`/latest/client-channels`](recursos/client-channels.md) | Canales asociados a cada cliente. |
| [`/latest/credits`](recursos/credits.md) | Personas y créditos artísticos referenciados por el contenido. |
| [`/latest/programs`](recursos/programs.md) | Programas y sus metadatos editoriales. |
| [`/latest/episodes`](recursos/episodes.md) | Episodios o capítulos asociados a los programas. |
| [`/latest/seasons`](recursos/seasons.md) | Temporadas asociadas a los programas. |
| [`/latest/schedule`](recursos/schedule.md) | Grilla de programación ordenada por canal y fecha de inicio. |
| [`/latest/countries`](recursos/countries.md) | Países referenciados por los demás recursos. |
| [`/latest/channel-categories`](recursos/channel-categories.md) | Categorías utilizadas para clasificar señales. |
| [`/latest/vod`](recursos/vod.md) | Disponibilidad de contenidos bajo demanda. |

El prefijo completo de cada endpoint es:

```text
/api/v1/rtv/processes/{processId}
```

Por ejemplo, el endpoint completo de programación es:

```http
GET /api/v1/rtv/processes/123/latest/schedule
```

## Respuesta

Las respuestas exitosas utilizan `application/json` y se envían comprimidas con
GZIP. La mayoría de los clientes HTTP realiza la descompresión automáticamente.

Encabezados relevantes:

- `Content-Encoding: gzip`
- `ETag`: identificador de la versión del recurso.
- `X-Generation-Id`: identificador interno de la actualización entregada.

Ejemplo con curl:

```bash
curl --compressed \
  "https://api.ejemplo.com/api/v1/rtv/processes/123/latest/programs"
```

## Estados HTTP

- `200 OK`: recurso encontrado.
- `400 Bad Request`: proceso, fecha o recurso inválido.
- `404 Not Found`: todavía no existe una actualización para la consulta.
- `500 Internal Server Error`: error inesperado del servicio.
