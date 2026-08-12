---
title: "Category–genre relationships"
description: "Valid associations between categories and genres."
lang: en
translation_path: "recursos/category-genres.html"
---

# Category–genre relationships

Valid associations between categories and genres.

```http
GET /api/v1/rtv/processes/{processId}/latest/category-genres
```

## Response format

```json
{
  "categories_genres": [
    {
      "category_id": 1,
      "genre_id": 5
    }
  ]
}
```

## Exposed data

| Field | Type | Description |
|---|---|---|
| `category_id` | integer | Category identifier. |
| `genre_id` | integer | Genre identifier. |

## Considerations

- `genre_id` may use the equivalent-genre catalog configured for the process.

[Back to the client guide](../API_CLIENTES.md)
