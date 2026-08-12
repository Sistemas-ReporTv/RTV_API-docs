---
title: "Conteúdo VOD"
description: "Disponibilidade de conteúdos sob demanda."
lang: pt
translation_path: "recursos/vod.html"
---

# Conteúdo VOD

Disponibilidade de conteúdos sob demanda.

```http
GET /api/v1/rtv/processes/{processId}/latest/vod
```

## Formato da resposta

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

## Dados expostos

| Campo | Tipo | Descrição |
|---|---|---|
| `channel_id` | inteiro | Identificador do canal. |
| `program_id` | inteiro | Identificador do programa. |
| `episode_id` | inteiro | Identificador do episódio. |
| `season_id` | inteiro | Identificador da temporada. |
| `available_date` | objeto | Período de disponibilidade. |
| `available_date.start_date` | texto | Início no formato `AAAA-MM-DD HH:mm:ss`. |
| `available_date.end_date` | texto | Fim no formato `AAAA-MM-DD HH:mm:ss`. |
| `internal_id` | texto | Identificador interno do conteúdo. |
| `provider` | texto | Provedor ou distribuidor. |

## Considerações

- Somente são publicados itens que atendem às condições de disponibilidade e imagens do processo.

[Voltar ao guia para clientes](../API_CLIENTES.md)
