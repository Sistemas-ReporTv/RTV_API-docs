---
title: "Credits"
description: "People and artistic credits referenced by the content."
lang: en
translation_path: "recursos/credits.html"
---

# Credits

People and artistic credits referenced by the content.

```http
GET /api/v1/rtv/processes/{processId}/latest/credits
```

## Response format

```json
{
  "credits": [
    {
      "type": "Actor",
      "id": 45,
      "name": "Persona ejemplo",
      "country": 32,
      "birth": "15/04/1980",
      "gender": "F",
      "character": "Personaje",
      "images": [
        {
          "width": 300,
          "height": 450,
          "primary": true,
          "url": "https://imagenes.ejemplo.com/45.jpg"
        }
      ]
    }
  ]
}
```

## Exposed data

| Field | Type | Description |
|---|---|---|
| `type` | string | Participation type. |
| `id` | integer | Person identifier. |
| `name` | string | Person name. |
| `country` | integer | Country-of-origin identifier. |
| `birth` | string | Birth date in `DD/MM/YYYY` format. |
| `gender` | string | Reported gender. |
| `character` | string | Character portrayed. |
| `images` | array | Images associated with the credit. |
| `images[].width` | integer | Image width in pixels. |
| `images[].height` | integer | Image height in pixels. |
| `images[].primary` | boolean | Whether this is the primary image. |
| `images[].url` | string | Public image URL. |

## Considerations

- `images` is included only when credit images are enabled for the process.

[Back to the client guide](../API_CLIENTES.md)
