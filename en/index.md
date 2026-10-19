---
title: "Home"
description: "RTV API lets you retrieve the latest available update for RTV scheduling and content data. Responses are delivered as JSON and compressed with GZIP."
permalink: /en/
lang: en
translation_path: ""
---

# RTV API Documentation

RTV API lets you retrieve the latest available update for RTV
scheduling and content data. Responses are delivered as JSON and
compressed with GZIP.

## Quick start

All resources use the same endpoint format:

```http
GET /api/v1/rtv/processes/{processId}/latest/{resource}
```

All requests require the client API token in the
`Authorization: Bearer TU_API_TOKEN` header. The [client guide](API_CLIENTES.md)
includes a cURL example.

Replace `{processId}` with the identifier assigned to your integration and
`{resource}` with the data set you need. For example:

```http
GET /api/v1/rtv/processes/123/latest/programs
```

You can also request the version generated for a specific date with the
optional `from` parameter, using the `YYYY-MM-DD` format:

```http
GET /api/v1/rtv/processes/123/latest/programs?from=2026-08-03
```

The [client guide](API_CLIENTES.md) contains request and response details,
headers, and HTTP statuses.

## Resources

### Content and scheduling

| Resource | Description |
|---|---|
| [Programs](resources/programs.md) | Programs and editorial metadata. |
| [Episodes](resources/episodes.md) | Episodes associated with programs. |
| [Seasons](resources/seasons.md) | Seasons associated with programs. |
| [Schedule](resources/schedule.md) | Schedule by channel and start date. |
| [Video on demand](resources/vod.md) | On-demand content availability. |
| [Credits](resources/credits.md) | People and artistic credits. |
| [Awards](resources/awards.md) | Awards catalog. |
| [Relationship types](resources/related-program-types.md) | Available relationships between programs. |

### Classification

| Resource | Description |
|---|---|
| [Categories](resources/categories.md) | Content categories. |
| [Genres](resources/genres.md) | Content genres. |
| [Subgenres](resources/subgenres.md) | Content subgenres. |
| [Categories and genres](resources/category-genres.md) | Valid associations between categories and genres. |
| [Genres and subgenres](resources/genre-subgenres.md) | Valid associations between genres and subgenres. |
| [Countries](resources/countries.md) | Countries referenced by other resources. |

### Channels and clients

| Resource | Description |
|---|---|
| [Channels](resources/channels.md) | Signals included in the process. |
| [Channel categories](resources/channel-categories.md) | Channel classification. |
| [Clients](resources/clients.md) | Clients enabled in the feed. |
| [Channels by client](resources/client-channels.md) | Channels associated with each client. |

### Sports

| Resource | Description |
|---|---|
| [Teams](resources/teams.md) | Available sports teams. |
| [Tournaments](resources/tournaments.md) | Tournaments and sports competitions. |
| [Stadiums](resources/stadiums.md) | Stadiums and sports venues. |
