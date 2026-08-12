---
title: "Tournaments"
description: "Available tournaments and sports competitions."
lang: en
translation_path: "recursos/tournaments.html"
---

# Tournaments

Available tournaments and sports competitions.

```http
GET /api/v1/rtv/processes/{processId}/latest/tournaments
```

## Response format

```json
{
  "tournaments": [
    {
      "id": 7,
      "name": "Torneo ejemplo",
      "description": "Descripción del torneo"
    }
  ]
}
```

## Exposed data

| Field | Type | Description |
|---|---|---|
| `id` | integer | Tournament identifier. |
| `name` | string | Tournament name. |
| `description` | string | Tournament description. |

[Back to the client guide](../API_CLIENTES.md)
