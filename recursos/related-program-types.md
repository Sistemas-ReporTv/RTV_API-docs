---
title: "Tipos de relación entre programas"
---

# Tipos de relación entre programas

Tipos utilizados para relacionar programas entre sí.

```http
GET /api/v1/rtv/processes/{processId}/latest/related-program-types
```

## Formato de respuesta

```json
{
  "related_program_types": [
    {
      "relation_type_id": 1,
      "value": "Relacionado"
    }
  ]
}
```

## Datos expuestos

| Campo | Tipo | Descripción |
|---|---|---|
| `relation_type_id` | entero | Identificador del tipo de relación. |
| `value` | texto | Descripción del tipo de relación. |

[Volver a la guía de clientes](../API_CLIENTES.md)
