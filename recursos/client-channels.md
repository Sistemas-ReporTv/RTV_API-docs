---
title: "Canales por cliente"
---

# Canales por cliente

Canales asociados a cada cliente.

```http
GET /api/v1/rtv/processes/{processId}/latest/client-channels
```

## Formato de respuesta

```json
{
  "client_channels": [
    {
      "client_id": 123,
      "channel_id": 15,
      "channel": 101,
      "short_name": "CEX",
      "name": "Canal ejemplo",
      "alignment_id": 2
    }
  ]
}
```

## Datos expuestos

| Campo | Tipo | Descripción |
|---|---|---|
| `client_id` | entero | Identificador del cliente. |
| `channel_id` | entero | Identificador del canal. |
| `channel` | entero | Número de canal asignado. |
| `short_name` | texto | Nombre corto del canal. |
| `name` | texto | Nombre del canal. |
| `alignment_id` | entero | Identificador de la alineación. |

[Volver a la guía de clientes](../API_CLIENTES.md)
