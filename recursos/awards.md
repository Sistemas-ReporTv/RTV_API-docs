# Premios

Catálogo de premios disponible.

```http
GET /api/v1/rtv/processes/{processId}/latest/awards
```

## Formato de respuesta

```json
{
  "awards": [
    {
      "id": 3,
      "value": "Premio ejemplo"
    }
  ]
}
```

## Datos expuestos

| Campo | Tipo | Descripción |
|---|---|---|
| `id` | entero | Identificador del premio. |
| `value` | texto | Descripción o nombre del premio. |

[Volver a la guía de clientes](../API_CLIENTES.md)
