---
title: "Clients"
description: "Clients enabled in the feed."
lang: en
translation_path: "recursos/clients.html"
---

# Clients

Clients enabled in the feed.

```http
GET /api/v1/rtv/processes/{processId}/latest/clients
```

## Response format

```json
{
  "clients": [
    {
      "id": 123,
      "name": "Cliente ejemplo",
      "country_id": 32
    }
  ]
}
```

## Exposed data

| Field | Type | Description |
|---|---|---|
| `id` | integer | Client identifier. |
| `name` | string | Business or display name. |
| `country_id` | integer | Country identifier. |

[Back to the client guide](../API_CLIENTES.md)
