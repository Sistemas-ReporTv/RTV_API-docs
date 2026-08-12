---
title: "Genre–subgenre relationships"
description: "Valid associations between genres and subgenres."
lang: en
translation_path: "recursos/genre-subgenres.html"
---

# Genre–subgenre relationships

Valid associations between genres and subgenres.

```http
GET /api/v1/rtv/processes/{processId}/latest/genre-subgenres
```

## Response format

```json
{
  "genres_subgenres": [
    {
      "genre_id": 5,
      "subgenre_id": 12
    }
  ]
}
```

## Exposed data

| Field | Type | Description |
|---|---|---|
| `genre_id` | integer | Genre identifier. |
| `subgenre_id` | integer | Subgenre identifier. |

## Considerations

- `genre_id` may use the equivalent-genre catalog configured for the process.

[Back to the client guide](../API_CLIENTES.md)
