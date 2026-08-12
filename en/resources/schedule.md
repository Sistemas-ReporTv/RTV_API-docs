---
title: "Schedule"
description: "Schedule ordered by channel and start date."
lang: en
translation_path: "recursos/schedule.html"
---

# Schedule

Schedule ordered by channel and start date.

```http
GET /api/v1/rtv/processes/{processId}/latest/schedule
```

## Response format

```json
{
  "schedule": [
    {
      "channel_id": 15,
      "start_date": "03/08/2026 21:00:00",
      "gmt_start_date": "04/08/2026 00:00:00",
      "runtime": 60,
      "program_id": 1001,
      "episode_id": 2001,
      "season_id": 3001,
      "transmition_type": "Estreno",
      "alternate_title": "Título alternativo",
      "dialog": "Original",
      "featured": "Sí",
      "available_subtitles_languages": [
        "Español"
      ],
      "available_audio_languages": [
        "Español"
      ],
      "audio_type": "Stereo",
      "SAP_available": "",
      "CC_available": ""
    }
  ]
}
```

## Exposed data

| Field | Type | Description |
|---|---|---|
| `channel_id` | integer | Channel identifier. |
| `start_date` | string | Local start in `DD/MM/YYYY HH:mm:ss` format. |
| `gmt_start_date` | string | GMT start in the same format. |
| `runtime` | integer | Duration in minutes. |
| `program_id` | integer | Program identifier. |
| `episode_id` | integer | Episode identifier. |
| `season_id` | integer | Season identifier. |
| `transmition_type` | string | Transmission type. |
| `alternate_title` | string | Alternate title. |
| `dialog` | string | Mode: `Doblado`, `Subtitulado` u `Original`. |
| `featured` | string | Reported featured value. |
| `available_subtitles_languages` | array of strings | Available subtitle languages. |
| `available_audio_languages` | array of strings | Available audio languages. |
| `audio_type` | string | Audio type. |
| `SAP_available` | string | SAP availability. |
| `CC_available` | string | Closed-caption availability. |

## Considerations

- Depending on the configuration, the following fields may be added: `event_id`, `price_value`, `alternate_title_eng` and `alternate_title_prt`.
- When alternate episode or season data exists, the following fields may be added: `episode_alt_title`, `episode_alt_title_eng`, `episode_alt_title_prt`, `episode_alt_num`, `season_alt_title` and `season_alt_num`.

[Back to the client guide](../API_CLIENTES.md)
