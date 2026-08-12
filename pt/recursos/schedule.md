---
title: "Programação"
description: "Grade de programação ordenada por canal e data de início."
lang: pt
translation_path: "recursos/schedule.html"
---

# Programação

Grade de programação ordenada por canal e data de início.

```http
GET /api/v1/rtv/processes/{processId}/latest/schedule
```

## Formato da resposta

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

## Dados expostos

| Campo | Tipo | Descrição |
|---|---|---|
| `channel_id` | inteiro | Identificador do canal. |
| `start_date` | texto | Início local no formato `DD/MM/AAAA HH:mm:ss`. |
| `gmt_start_date` | texto | Início GMT no mesmo formato. |
| `runtime` | inteiro | Duração em minutos. |
| `program_id` | inteiro | Identificador do programa. |
| `episode_id` | inteiro | Identificador do episódio. |
| `season_id` | inteiro | Identificador da temporada. |
| `transmition_type` | texto | Tipo de transmissão. |
| `alternate_title` | texto | Título alternativo. |
| `dialog` | texto | Modalidade: `Doblado`, `Subtitulado` u `Original`. |
| `featured` | texto | Valor de destaque informado. |
| `available_subtitles_languages` | array de textos | Idiomas de legendas disponíveis. |
| `available_audio_languages` | array de textos | Idiomas de áudio disponíveis. |
| `audio_type` | texto | Tipo de áudio. |
| `SAP_available` | texto | Disponibilidade de SAP. |
| `CC_available` | texto | Disponibilidade de closed captions. |

## Considerações

- Dependendo da configuração, podem ser adicionados: `event_id`, `price_value`, `alternate_title_eng` e `alternate_title_prt`.
- Quando existem dados alternativos do episódio ou da temporada, podem ser adicionados: `episode_alt_title`, `episode_alt_title_eng`, `episode_alt_title_prt`, `episode_alt_num`, `season_alt_title` e `season_alt_num`.

[Voltar ao guia para clientes](../API_CLIENTES.md)
