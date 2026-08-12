---
title: "Channels"
description: "Signals or channels included in the process."
lang: en
translation_path: "recursos/channels.html"
---

# Channels

Signals or channels included in the process.

```http
GET /api/v1/rtv/processes/{processId}/latest/channels
```

## Response format

```json
{
  "channels": [
    {
      "id": 15,
      "name": "Canal ejemplo",
      "country_id": 32,
      "channel_category_id": 2,
      "alternative_name": "CEX",
      "sintony": 101,
      "hd": true,
      "logos": [
        {
          "width": 400,
          "height": 200,
          "url": "https://imagenes.ejemplo.com/100.jpg"
        }
      ]
    }
  ]
}
```

## Exposed data

| Field | Type | Description |
|---|---|---|
| `id` | integer | Channel identifier. |
| `name` | string | Channel name. |
| `country_id` | integer | Country identifier. |
| `channel_category_id` | integer | Channel category identifier. |
| `alternative_name` | string | Short name or abbreviation. |
| `sintony` | integer | Tuning number. |
| `hd` | boolean | Whether the signal is HD. |
| `logos` | array | Logos available for the channel. |
| `logos[].width` | integer | Image width in pixels. |
| `logos[].height` | integer | Image height in pixels. |
| `logos[].url` | string | Public image URL. |

## Considerations

- The name may be normalized according to the process configuration.

[Back to the client guide](../API_CLIENTES.md)
