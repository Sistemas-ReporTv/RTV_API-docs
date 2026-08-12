---
title: "Contenido VOD"
description: "Disponibilidad de contenidos bajo demanda."
lang: es
translation_path: "recursos/vod.html"
---

# Contenido VOD

Disponibilidad de contenidos bajo demanda.

```http
GET /api/v1/rtv/processes/{processId}/latest/vod
```

## Formato de respuesta

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

## Datos expuestos

| Campo | Tipo | Descripción |
|---|---|---|
| `channel_id` | entero | Identificador del canal. |
| `program_id` | entero | Identificador del programa. |
| `episode_id` | entero | Identificador del episodio. |
| `season_id` | entero | Identificador de la temporada. |
| `available_date` | objeto | Período de disponibilidad. |
| `available_date.start_date` | texto | Inicio con formato `AAAA-MM-DD HH:mm:ss`. |
| `available_date.end_date` | texto | Fin con formato `AAAA-MM-DD HH:mm:ss`. |
| `internal_id` | texto | Identificador interno del contenido. |
| `provider` | texto | Proveedor o distribuidor. |

## Consideraciones

- Sólo se publican elementos que cumplen las condiciones de disponibilidad e imágenes del proceso.

[Volver a la guía de clientes](../API_CLIENTES.md)
