---
title: "Stadiums"
description: "Available stadiums and sports venues."
lang: en
translation_path: "recursos/stadiums.html"
---

# Stadiums

Available stadiums and sports venues.

```http
GET /api/v1/rtv/processes/{processId}/latest/stadiums
```

## Response format

```json
{
  "stadiums": [
    {
      "id": 4,
      "name": "Estadio ejemplo",
      "location": "Buenos Aires"
    }
  ]
}
```

## Exposed data

| Field | Type | Description |
|---|---|---|
| `id` | integer | Stadium identifier. |
| `name` | string | Stadium name. |
| `location` | string | Reported location. |

[Back to the client guide](../API_CLIENTES.md)
