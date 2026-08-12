---
title: "Relaciones entre categorías y géneros"
description: "Asociaciones válidas entre categorías y géneros."
lang: es
translation_path: "recursos/category-genres.html"
---

# Relaciones entre categorías y géneros

Asociaciones válidas entre categorías y géneros.

```http
GET /api/v1/rtv/processes/{processId}/latest/category-genres
```

## Formato de respuesta

```json
{
  "categories_genres": [
    {
      "category_id": 1,
      "genre_id": 5
    }
  ]
}
```

## Datos expuestos

| Campo | Tipo | Descripción |
|---|---|---|
| `category_id` | entero | Identificador de la categoría. |
| `genre_id` | entero | Identificador del género. |

## Consideraciones

- `genre_id` puede utilizar el catálogo de géneros equivalentes configurado para el proceso.

[Volver a la guía de clientes](../API_CLIENTES.md)
