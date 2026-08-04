# Estadios

Estadios y sedes deportivas disponibles.

```http
GET /api/v1/rtv/processes/{processId}/latest/stadiums
```

## Formato de respuesta

```json
{
  "stadiums": [
    {
      "id": 4,
      "name": "Estadio ejemplo",
      "location": "Buenos Aires"
    }
  ]
}
```

## Datos expuestos

| Campo | Tipo | Descripción |
|---|---|---|
| `id` | entero | Identificador del estadio. |
| `name` | texto | Nombre del estadio. |
| `location` | texto | Ubicación informada. |

[Volver a la guía de clientes](../API_CLIENTES.md)
