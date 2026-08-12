---
title: "Program relationship types"
description: "Types used to relate programs to one another."
lang: en
translation_path: "recursos/related-program-types.html"
---

# Program relationship types

Types used to relate programs to one another.

```http
GET /api/v1/rtv/processes/{processId}/latest/related-program-types
```

## Response format

```json
{
  "related_program_types": [
    {
      "relation_type_id": 1,
      "value": "Relacionado"
    }
  ]
}
```

## Exposed data

| Field | Type | Description |
|---|---|---|
| `relation_type_id` | integer | Relationship type identifier. |
| `value` | string | Relationship type description. |

[Back to the client guide](../API_CLIENTES.md)
