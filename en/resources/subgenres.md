---
title: "Subgenres"
description: "Subgenres used to classify content."
lang: en
translation_path: "recursos/subgenres.html"
---

# Subgenres

Subgenres used to classify content.

```http
GET /api/v1/rtv/processes/{processId}/latest/subgenres
```

## Response format

```json
{
  "subgenres": [
    {
      "id": 12,
      "name": "Fútbol",
      "name_eng": "Football",
      "name_prt": "Futebol"
    }
  ]
}
```

## Exposed data

| Field | Type | Description |
|---|---|---|
| `id` | integer | Subgenre identifier. |
| `name` | string | Name in Spanish. |
| `name_eng` | string | Name in English. |
| `name_prt` | string | Name in Portuguese. |

## Considerations

- `name_eng` and `name_prt` are included when additional languages are enabled for the process.

[Back to the client guide](../API_CLIENTES.md)
