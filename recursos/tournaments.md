---
title: "Torneos"
description: "Torneos y competencias deportivas disponibles."
lang: es
translation_path: "recursos/tournaments.html"
---

# Torneos

Torneos y competencias deportivas disponibles.

```http
GET /api/v1/rtv/processes/{processId}/latest/tournaments
```

## Formato de respuesta

```json
{
  "tournaments": [
    {
      "id": 7,
      "name": "Torneo ejemplo",
      "description": "Descripción del torneo"
    }
  ]
}
```

## Datos expuestos

| Campo | Tipo | Descripción |
|---|---|---|
| `id` | entero | Identificador del torneo. |
| `name` | texto | Nombre del torneo. |
| `description` | texto | Descripción del torneo. |

[Volver a la guía de clientes](../API_CLIENTES.md)
