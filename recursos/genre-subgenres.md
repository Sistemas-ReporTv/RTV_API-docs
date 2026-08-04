# Relaciones entre géneros y subgéneros

Asociaciones válidas entre géneros y subgéneros.

```http
GET /api/v1/rtv/processes/{processId}/latest/genre-subgenres
```

## Formato de respuesta

```json
{
  "genres_subgenres": [
    {
      "genre_id": 5,
      "subgenre_id": 12
    }
  ]
}
```

## Datos expuestos

| Campo | Tipo | Descripción |
|---|---|---|
| `genre_id` | entero | Identificador del género. |
| `subgenre_id` | entero | Identificador del subgénero. |

## Consideraciones

- `genre_id` puede utilizar el catálogo de géneros equivalentes configurado para el proceso.

[Volver a la guía de clientes](../API_CLIENTES.md)
