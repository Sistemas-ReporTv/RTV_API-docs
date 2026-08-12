---
title: "VOD content"
description: "On-demand content availability."
lang: en
translation_path: "recursos/vod.html"
---

# VOD content

On-demand content availability.

```http
GET /api/v1/rtv/processes/{processId}/latest/vod
```

## Response format

```json
{
  "vod": [
    {
      "channel_id": 15,
      "program_id": 1001,
      "episode_id": 2001,
      "season_id": 3001,
      "available_date": {
        "start_date": "2026-08-03 00:00:00",
        "end_date": "2026-08-10 23:59:59"
      },
      "internal_id": "MEDIA-123",
      "provider": "Proveedor ejemplo"
    }
  ]
}
```

## Exposed data

| Field | Type | Description |
|---|---|---|
| `channel_id` | integer | Channel identifier. |
| `program_id` | integer | Program identifier. |
| `episode_id` | integer | Episode identifier. |
| `season_id` | integer | Season identifier. |
| `available_date` | object | Availability period. |
| `available_date.start_date` | string | Start in `YYYY-MM-DD HH:mm:ss` format. |
| `available_date.end_date` | string | End in `YYYY-MM-DD HH:mm:ss` format. |
| `internal_id` | string | Internal content identifier. |
| `provider` | string | Provider or distributor. |

## Considerations

- Only items that meet the process availability and image requirements are published.

[Back to the client guide](../API_CLIENTES.md)
