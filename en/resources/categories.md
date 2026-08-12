---
title: "Categories"
description: "Categories used to classify content."
lang: en
translation_path: "recursos/categories.html"
---

# Categories

Categories used to classify content.

```http
GET /api/v1/rtv/processes/{processId}/latest/categories
```

## Response format

```json
{
  "categories": [
    {
      "id": 1,
      "name": "Películas",
      "name_eng": "Movies",
      "name_prt": "Filmes"
    }
  ]
}
```

## Exposed data

| Field | Type | Description |
|---|---|---|
| `id` | integer | Category identifier. |
| `name` | string | Name in Spanish. |
| `name_eng` | string | Name in English. |
| `name_prt` | string | Name in Portuguese. |

## Considerations

- `name_eng` and `name_prt` are included when additional languages are enabled for the process.

[Back to the client guide](../API_CLIENTES.md)
