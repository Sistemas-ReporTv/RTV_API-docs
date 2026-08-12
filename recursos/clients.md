---
title: "Clientes"
description: "Clientes habilitados en el feed."
lang: es
translation_path: "recursos/clients.html"
---

# Clientes

Clientes habilitados en el feed.

```http
GET /api/v1/rtv/processes/{processId}/latest/clients
```

## Formato de respuesta

```json
{
  "clients": [
    {
      "id": 123,
      "name": "Cliente ejemplo",
      "country_id": 32
    }
  ]
}
```

## Datos expuestos

| Campo | Tipo | Descripción |
|---|---|---|
| `id` | entero | Identificador del cliente. |
| `name` | texto | Razón social o nombre. |
| `country_id` | entero | Identificador del país. |

[Volver a la guía de clientes](../API_CLIENTES.md)
