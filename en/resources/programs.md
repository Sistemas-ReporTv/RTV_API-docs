---
title: "Programs"
description: "Programs and their editorial metadata."
lang: en
translation_path: "recursos/programs.html"
---

# Programs

Programs and their editorial metadata.

```http
GET /api/v1/rtv/processes/{processId}/latest/programs
```

## Response format

```json
{
  "programs": [
    {
      "id": 1001,
      "sport_event": false,
      "main_title": "Programa ejemplo",
      "original_title": "Original title",
      "long_argument": {
        "lang": "spa",
        "value": "Descripción extensa"
      },
      "short_argument": {
        "lang": "spa",
        "value": "Descripción breve"
      },
      "year": 2026,
      "parental_rating": {
        "type": "VCHIP",
        "value": "ATP"
      },
      "long_description": {
        "lang": "eng",
        "value": "Long description"
      },
      "short_description": {
        "lang": "eng",
        "value": "Short description"
      },
      "images": [
        {
          "width": 600,
          "height": 900,
          "primary": true,
          "url": "https://imagenes.ejemplo.com/1001.jpg",
          "poster": true
        }
      ],
      "keywords": [
        "ejemplo"
      ],
      "related_programs": [
        {
          "type_id": 1,
          "program_id": 1002
        }
      ],
      "references": [
        {
          "type": "category",
          "id": 1
        },
        {
          "type": "genre",
          "id": 5
        }
      ]
    }
  ]
}
```

## Exposed data

| Field | Type | Description |
|---|---|---|
| `id` | integer | Program identifier. |
| `imdb_id` | string | IMDb identifier, when enabled and available. |
| `imdb_rating` | number | IMDb rating, greater than 0 and up to 10, when enabled and available. |
| `sport_event` | boolean | Whether this is a sports event. |
| `main_title` | string | Main title. |
| `original_title` | string | Original title. |
| `long_argument` | object | Long synopsis in Spanish (`lang` and `value`). |
| `short_argument` | object | Short synopsis in Spanish (`lang` and `value`). |
| `year` | integer | Content year. |
| `parental_rating` | object | Parental rating: `type` and `value`. |
| `long_description` | object | Long description in English (`lang` and `value`). |
| `short_description` | object | Short description in English (`lang` and `value`). |
| `images` | array | Program images. |
| `images[].width` | integer | Width in pixels. |
| `images[].height` | integer | Height in pixels. |
| `images[].primary` | boolean | Whether this is primary. |
| `images[].url` | string | Image reference for the agreed delivery method; see [image delivery](../API_CLIENTES.md). |
| `images[].poster` | boolean | Whether the format is a poster. |
| `keywords` | array of strings | Associated keywords. |
| `related_programs` | array | Related programs. |
| `related_programs[].type_id` | integer | Relationship type. |
| `related_programs[].program_id` | integer | Related program. |
| `references` | array | References to category, genre, subgenre, actors, directors, and country. |
| `references[].type` | string | Reference type. |
| `references[].id` | integer or string | Identifier or list of identifiers. |

## Considerations

- `imdb_id` and `imdb_rating` are optional and may be omitted independently depending on configuration and available data.
- `poster` is included when that attribute is enabled for the process.
- When additional languages are enabled, the following fields are added: `main_title_eng`, `main_title_prt`, `original_title_eng`, `original_title_prt`, `long_argument_prt` and `short_argument_prt`.

[Back to the client guide](../API_CLIENTES.md)
