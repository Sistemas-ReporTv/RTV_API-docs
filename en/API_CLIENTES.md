---
title: "RTV API — Client Guide"
description: "The API lets you retrieve the latest available version of each RTV data set. Replace `{processId}` with the process identifier assigned to your integration."
lang: en
translation_path: "API_CLIENTES.html"
---

# RTV API — Client Guide

The API lets you retrieve the latest available version of each RTV data set.
Replace `{processId}` with the process identifier assigned to your
integration.

## Request

```http
GET /api/v1/rtv/processes/{processId}/latest/{resource}
```

The latest update is returned by default. To request the version
generated for a specific date, add the optional `from` parameter:

```http
GET /api/v1/rtv/processes/123/latest/programs?from=2026-08-03
```

The date uses the `YYYY-MM-DD` format.

## Available resources

Each resource has a page describing its response format and
the data it exposes.

| Resource and documentation | Content |
|---|---|
| [`/latest/teams`](resources/teams.md) | Sports teams available to the process. |
| [`/latest/tournaments`](resources/tournaments.md) | Available tournaments and sports competitions. |
| [`/latest/stadiums`](resources/stadiums.md) | Available stadiums and sports venues. |
| [`/latest/awards`](resources/awards.md) | Available awards catalog. |
| [`/latest/related-program-types`](resources/related-program-types.md) | Types used to relate programs to one another. |
| [`/latest/channels`](resources/channels.md) | Signals or channels included in the process. |
| [`/latest/categories`](resources/categories.md) | Categories used to classify content. |
| [`/latest/genres`](resources/genres.md) | Genres used to classify content. |
| [`/latest/subgenres`](resources/subgenres.md) | Subgenres used to classify content. |
| [`/latest/genre-subgenres`](resources/genre-subgenres.md) | Valid associations between genres and subgenres. |
| [`/latest/category-genres`](resources/category-genres.md) | Valid associations between categories and genres. |
| [`/latest/clients`](resources/clients.md) | Clients enabled in the feed. |
| [`/latest/client-channels`](resources/client-channels.md) | Channels associated with each client. |
| [`/latest/credits`](resources/credits.md) | People and artistic credits referenced by the content. |
| [`/latest/programs`](resources/programs.md) | Programs and their editorial metadata. |
| [`/latest/episodes`](resources/episodes.md) | Episodes associated with programs. |
| [`/latest/seasons`](resources/seasons.md) | Seasons associated with programs. |
| [`/latest/schedule`](resources/schedule.md) | Schedule ordered by channel and start date. |
| [`/latest/countries`](resources/countries.md) | Countries referenced by other resources. |
| [`/latest/channel-categories`](resources/channel-categories.md) | Categories used to classify channels. |
| [`/latest/vod`](resources/vod.md) | On-demand content availability. |

The full prefix for every endpoint is:

```text
/api/v1/rtv/processes/{processId}
```

For example, the full schedule endpoint is:

```http
GET /api/v1/rtv/processes/123/latest/schedule
```

## Response

Successful responses use `application/json` and are compressed with
GZIP. Most HTTP clients decompress them automatically.

Relevant headers:

- `Content-Encoding: gzip`
- `ETag`: resource version identifier.
- `X-Generation-Id`: internal identifier of the delivered update.

curl example:

```bash
curl --compressed \
  "https://api.ejemplo.com/api/v1/rtv/processes/123/latest/programs"
```

## HTTP statuses

- `200 OK`: resource found.
- `400 Bad Request`: invalid process, date, or resource.
- `404 Not Found`: no update exists for the request yet.
- `500 Internal Server Error`: unexpected service error.
