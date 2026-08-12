---
title: "Equipos"
description: "Equipos deportivos disponibles para el proceso."
lang: es
translation_path: "recursos/teams.html"
---

# Equipos

Equipos deportivos disponibles para el proceso.

```http
GET /api/v1/rtv/processes/{processId}/latest/teams
```

## Formato de respuesta

```json
{
  "teams": [
    {
      "id": 10,
      "name": "Equipo ejemplo",
      "stadium_id": 4,
      "county_id": 32
    }
  ]
}
```

## Datos expuestos

| Campo | Tipo | Descripción |
|---|---|---|
| `id` | entero | Identificador del equipo. |
| `name` | texto | Nombre del equipo. |
| `stadium_id` | entero | Identificador del estadio asociado. |
| `county_id` | entero | Identificador del país. El nombre histórico se conserva por compatibilidad. |

[Volver a la guía de clientes](../API_CLIENTES.md)
