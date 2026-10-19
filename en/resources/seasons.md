---
title: "Seasons"
description: "Seasons associated with programs."
lang: en
translation_path: "recursos/seasons.html"
---

# Seasons

Seasons associated with programs.

```http
GET /api/v1/rtv/processes/{processId}/latest/seasons
```

## Response format

```json
{
  "seasons": [
    {
      "id": 3001,
      "title": "Temporada 1",
      "number": 1,
      "argument": "Descripción de la temporada",
      "references": [
        {
          "type": "director",
          "id": "50"
        }
      ],
      "images": [
        {
          "width": 600,
          "height": 900,
          "primary": true,
          "url": "https://imagenes.ejemplo.com/3001.jpg"
        }
      ]
    }
  ]
}
```

## Exposed data

| Field | Type | Description |
|---|---|---|
| `id` | integer | Season identifier. |
| `title` | string | Title or description. |
| `number` | integer | Season number. |
| `argument` | string | Season synopsis. |
| `references` | array | References to actors and directors. |
| `references[].type` | string | Reference type. |
| `references[].id` | string | Comma-separated identifiers. |
| `images` | array | Season images. |
| `images[].width` | integer | Image width in pixels. |
| `images[].height` | integer | Image height in pixels. |
| `images[].primary` | boolean | Whether this is the primary image. |
| `images[].url` | string | Image reference for the agreed delivery method; see [image delivery](../API_CLIENTES.md). |

## Considerations

- When additional languages are enabled, the following fields are added: `title_eng`, `title_prt`, `argument_eng` and `argument_prt`.

[Back to the client guide](../API_CLIENTES.md)
