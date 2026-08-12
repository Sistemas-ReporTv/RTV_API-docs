---
title: "Géneros"
description: "Géneros utilizados para clasificar el contenido."
lang: es
translation_path: "recursos/genres.html"
---

# Géneros

Géneros utilizados para clasificar el contenido.

```http
GET /api/v1/rtv/processes/{processId}/latest/genres
```

## Formato de respuesta

```json
{
  "genres": [
    {
      "id": 5,
      "name": "Deportes",
      "name_eng": "Sports",
      "name_prt": "Esportes"
    }
  ]
}
```

## Datos expuestos

| Campo | Tipo | Descripción |
|---|---|---|
| `id` | entero | Identificador del género. |
| `name` | texto | Nombre en español. |
| `name_eng` | texto | Nombre en inglés. |
| `name_prt` | texto | Nombre en portugués. |

## Consideraciones

- `name_eng` y `name_prt` se incluyen cuando están habilitados los idiomas adicionales.
- Los identificadores y nombres pueden corresponder al catálogo de géneros equivalentes configurado para el proceso.

[Volver a la guía de clientes](../API_CLIENTES.md)
