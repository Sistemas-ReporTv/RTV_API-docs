---
title: "Categorías"
description: "Categorías utilizadas para clasificar el contenido."
lang: es
translation_path: "recursos/categories.html"
---

# Categorías

Categorías utilizadas para clasificar el contenido.

```http
GET /api/v1/rtv/processes/{processId}/latest/categories
```

## Formato de respuesta

```json
{
  "categories": [
    {
      "id": 1,
      "name": "Películas",
      "name_eng": "Movies",
      "name_prt": "Filmes"
    }
  ]
}
```

## Datos expuestos

| Campo | Tipo | Descripción |
|---|---|---|
| `id` | entero | Identificador de la categoría. |
| `name` | texto | Nombre en español. |
| `name_eng` | texto | Nombre en inglés. |
| `name_prt` | texto | Nombre en portugués. |

## Consideraciones

- `name_eng` y `name_prt` se incluyen cuando el proceso tiene habilitados los idiomas adicionales.

[Volver a la guía de clientes](../API_CLIENTES.md)
