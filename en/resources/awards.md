---
title: "Awards"
description: "Available awards catalog."
lang: en
translation_path: "recursos/awards.html"
---

# Awards

Available awards catalog.

```http
GET /api/v1/rtv/processes/{processId}/latest/awards
```

## Response format

```json
{
  "awards": [
    {
      "id": 3,
      "value": "Premio ejemplo"
    }
  ]
}
```

## Exposed data

| Field | Type | Description |
|---|---|---|
| `id` | integer | Award identifier. |
| `value` | string | Award description or name. |

[Back to the client guide](../API_CLIENTES.md)
