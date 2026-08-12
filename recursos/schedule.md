---
title: "Programación"
description: "Grilla de programación ordenada por canal y fecha de inicio."
lang: es
translation_path: "recursos/schedule.html"
---

# Programación

Grilla de programación ordenada por canal y fecha de inicio.

```http
GET /api/v1/rtv/processes/{processId}/latest/schedule
```

## Formato de respuesta

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

## Datos expuestos

| Campo | Tipo | Descripción |
|---|---|---|
| `channel_id` | entero | Identificador del canal. |
| `start_date` | texto | Inicio local con formato `DD/MM/AAAA HH:mm:ss`. |
| `gmt_start_date` | texto | Inicio GMT con el mismo formato. |
| `runtime` | entero | Duración en minutos. |
| `program_id` | entero | Identificador del programa. |
| `episode_id` | entero | Identificador del episodio. |
| `season_id` | entero | Identificador de la temporada. |
| `transmition_type` | texto | Tipo de transmisión. |
| `alternate_title` | texto | Título alternativo. |
| `dialog` | texto | Modalidad: `Doblado`, `Subtitulado` u `Original`. |
| `featured` | texto | Valor destacado informado. |
| `available_subtitles_languages` | arreglo de textos | Idiomas de subtítulos disponibles. |
| `available_audio_languages` | arreglo de textos | Idiomas de audio disponibles. |
| `audio_type` | texto | Tipo de audio. |
| `SAP_available` | texto | Disponibilidad SAP. |
| `CC_available` | texto | Disponibilidad de closed captions. |

## Consideraciones

- Según la configuración pueden agregarse `event_id`, `price_value`, `alternate_title_eng` y `alternate_title_prt`.
- Cuando existen datos alternativos del episodio o temporada pueden agregarse `episode_alt_title`, `episode_alt_title_eng`, `episode_alt_title_prt`, `episode_alt_num`, `season_alt_title` y `season_alt_num`.

[Volver a la guía de clientes](../API_CLIENTES.md)
