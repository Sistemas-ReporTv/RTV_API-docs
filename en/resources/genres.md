---
title: "Genres"
description: "Genres used to classify content."
lang: en
translation_path: "recursos/genres.html"
---

# Genres

Genres used to classify content.

```http
GET /api/v1/rtv/processes/{processId}/latest/genres
```

## Response format

```json
{
  "genres": [
    {
      "id": 5,
      "name": "Deportes",
      "name_eng": "Sports",
      "name_prt": "Esportes"
    }
  ]
}
```

## Exposed data

| Field | Type | Description |
|---|---|---|
| `id` | integer | Genre identifier. |
| `name` | string | Name in Spanish. |
| `name_eng` | string | Name in English. |
| `name_prt` | string | Name in Portuguese. |

## Considerations

- `name_eng` and `name_prt` are included when additional languages are enabled.
- Identifiers and names may come from the equivalent-genre catalog configured for the process.

[Back to the client guide](../API_CLIENTES.md)
