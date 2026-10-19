---
title: "Inicio"
description: "RTV API permite consultar la última actualización disponible de los datos de programación y contenidos RTV. Las respuestas se entregan en formato JSON y se comprimen con GZIP."
permalink: /
lang: es
translation_path: ""
---

# Documentación de RTV API

RTV API permite consultar la última actualización disponible de los datos de
programación y contenidos RTV. Las respuestas se entregan en formato JSON y se
comprimen con GZIP.

## Inicio rápido

Todos los recursos se consultan mediante el mismo formato de endpoint:

```http
GET /api/v1/rtv/processes/{processId}/latest/{resource}
```

Todas las consultas requieren el API token del cliente en el encabezado
`Authorization: Bearer TU_API_TOKEN`. La [guía para clientes](API_CLIENTES.md)
incluye un ejemplo con cURL.

Reemplazá `{processId}` por el identificador asignado a tu integración y
`{resource}` por el conjunto de datos que necesitás. Por ejemplo:

```http
GET /api/v1/rtv/processes/123/latest/programs
```

También podés pedir la versión generada para una fecha determinada con el
parámetro opcional `from`, en formato `AAAA-MM-DD`:

```http
GET /api/v1/rtv/processes/123/latest/programs?from=2026-08-03
```

La [guía para clientes](API_CLIENTES.md) contiene los detalles de consulta,
respuesta, encabezados y estados HTTP.

## Recursos

### Contenidos y programación

| Recurso | Descripción |
|---|---|
| [Programas](recursos/programs.md) | Programas y metadatos editoriales. |
| [Episodios](recursos/episodes.md) | Episodios asociados a los programas. |
| [Temporadas](recursos/seasons.md) | Temporadas asociadas a los programas. |
| [Programación](recursos/schedule.md) | Grilla por canal y fecha de inicio. |
| [Video bajo demanda](recursos/vod.md) | Disponibilidad de contenidos bajo demanda. |
| [Créditos](recursos/credits.md) | Personas y créditos artísticos. |
| [Premios](recursos/awards.md) | Catálogo de premios. |
| [Tipos de relación](recursos/related-program-types.md) | Relaciones disponibles entre programas. |

### Clasificación

| Recurso | Descripción |
|---|---|
| [Categorías](recursos/categories.md) | Categorías de contenido. |
| [Géneros](recursos/genres.md) | Géneros de contenido. |
| [Subgéneros](recursos/subgenres.md) | Subgéneros de contenido. |
| [Categorías y géneros](recursos/category-genres.md) | Asociaciones válidas entre categorías y géneros. |
| [Géneros y subgéneros](recursos/genre-subgenres.md) | Asociaciones válidas entre géneros y subgéneros. |
| [Países](recursos/countries.md) | Países referenciados por otros recursos. |

### Canales y clientes

| Recurso | Descripción |
|---|---|
| [Canales](recursos/channels.md) | Señales incluidas en el proceso. |
| [Categorías de canales](recursos/channel-categories.md) | Clasificación de las señales. |
| [Clientes](recursos/clients.md) | Clientes habilitados en el feed. |
| [Canales por cliente](recursos/client-channels.md) | Canales asociados a cada cliente. |

### Deportes

| Recurso | Descripción |
|---|---|
| [Equipos](recursos/teams.md) | Equipos deportivos disponibles. |
| [Torneos](recursos/tournaments.md) | Torneos y competencias deportivas. |
| [Estadios](recursos/stadiums.md) | Estadios y sedes deportivas. |
