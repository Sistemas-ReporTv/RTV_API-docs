---
title: "Episodes"
description: "Episodes associated with programs."
lang: en
translation_path: "recursos/episodes.html"
---

# Episodes

Episodes associated with programs.

```http
GET /api/v1/rtv/processes/{processId}/latest/episodes
```

## Response format

```json
{
  "episodes": [
    {
      "id": 2001,
      "program_id": 1001,
      "title": "Episodio ejemplo",
      "number": 1,
      "season_id": 3001,
      "long_argument": {
        "lang": "spa",
        "value": "Sinopsis"
      },
      "short_argument": {
        "lang": "spa",
        "value": "Resumen"
      },
      "long_description": {
        "lang": "eng",
        "value": "Synopsis"
      },
      "short_description": {
        "lang": "eng",
        "value": "Summary"
      },
      "references": [
        {
          "type": "actor",
          "id": "45,46"
        }
      ],
      "images": [
        {
          "width": 600,
          "height": 400,
          "primary": true,
          "url": "https://imagenes.ejemplo.com/2001.jpg"
        }
      ]
    }
  ]
}
```

## Exposed data

| Field | Type | Description |
|---|---|---|
| `id` | integer | Episode identifier. |
| `imdb_id` | string | IMDb identifier, when enabled and available. |
| `imdb_rating` | number | IMDb rating, greater than 0 and up to 10, when enabled and available. |
| `program_id` | integer | Program identifier. |
| `title` | string | Official title. |
| `number` | integer | Episode number. |
| `season_id` | integer | Season identifier. |
| `long_argument` | object | Long synopsis in Spanish (`lang` and `value`). |
| `short_argument` | object | Short synopsis in Spanish (`lang` and `value`). |
| `long_description` | object | Long description in English (`lang` and `value`). |
| `short_description` | object | Short description in English (`lang` and `value`). |
| `references` | array | References to actors and directors. |
| `references[].type` | string | Reference type. |
| `references[].id` | string | Comma-separated identifiers. |
| `images` | array | Episode images. |
| `images[].width` | integer | Image width in pixels. |
| `images[].height` | integer | Image height in pixels. |
| `images[].primary` | boolean | Whether this is the primary image. |
| `images[].url` | string | Image reference for the agreed delivery method; see [image delivery](../API_CLIENTES.md). |

## Considerations

- `imdb_id` and `imdb_rating` are optional and may be omitted independently depending on configuration and available data.
- When additional languages are enabled, the following fields are added: `title_eng`, `title_prt`, `long_argument_prt` and `short_argument_prt`.
- For sports events, `sportDetail` is added with `tournament`, `year`, `sport`, `stadium`, `round`, `team1`, `team2`, and `statistics`.

[Back to the client guide](../API_CLIENTES.md)
