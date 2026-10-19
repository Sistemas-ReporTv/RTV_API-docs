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

## Autenticación

Todas las consultas requieren el API token entregado para tu cliente. Enviá el
token en el encabezado `Authorization`, con el prefijo `Bearer`:

```http
Authorization: Bearer TU_API_TOKEN
```

El token permite consultar los procesos de tu cliente. No lo incluyas en la URL.

## Consulta

```http
GET /api/v1/rtv/processes/{processId}/latest/{resource}
```

Por defecto se devuelve la actualización más reciente. Para pedir la versión
generada para una fecha determinada, agregá el parámetro opcional `from`:

```http
GET /api/v1/rtv/processes/123/latest/programs?from=2026-08-03
```

### Parámetro opcional

| Parámetro | Formato | Comportamiento |
|---|---|---|
| `from` | Fecha `AAAA-MM-DD` | Selecciona la última actualización disponible generada para esa fecha exacta. Si se omite, devuelve la última actualización disponible del proceso. |

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
  -H "Authorization: Bearer TU_API_TOKEN" \
  "https://api.ejemplo.com/api/v1/rtv/processes/123/latest/programs"
```

Reemplazá `TU_API_TOKEN` por el token recibido, `123` por tu identificador de
proceso y `https://api.ejemplo.com` por la URL base informada para tu integración.
`--compressed` permite recibir y descomprimir la respuesta GZIP. Para consultar
una fecha determinada, agregá `?from=2026-08-03` al final de la URL.

## Entrega de imágenes

La entrega de imágenes se adapta a cada integración. Puede mantenerse el acceso
por URL o acordarse la subida a un destino del cliente mediante FTP, SFTP o
almacenamiento compatible con S3. Los formatos y las imágenes incluidas se definen
al configurar el proceso.

Según la modalidad acordada, el campo `url` de cada imagen o logo puede contener
una URL pública, una ruta relativa, un nombre de archivo o un identificador.
En todos los casos conserva el tipo texto.

## Opciones por integración

La integración puede incluir atributos opcionales, como `poster`, títulos y
sinopsis en idiomas adicionales, imágenes de créditos o datos adicionales de
programación. Se habilitan al configurar el proceso y se describen en las
consideraciones de cada recurso.

## Estados HTTP

- `200 OK`: recurso encontrado.
- `400 Bad Request`: proceso, fecha o recurso inválido.
- `401 Unauthorized`: el token falta, expiró, fue revocado o no es válido.
- `403 Forbidden`: el token no tiene acceso al proceso solicitado.
- `404 Not Found`: todavía no existe una actualización para la consulta.
- `500 Internal Server Error`: error inesperado del servicio.
