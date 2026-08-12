---
title: "Categorías de canales"
description: "Categorías utilizadas para clasificar señales."
lang: es
translation_path: "recursos/channel-categories.html"
---

# Categorías de canales

Categorías utilizadas para clasificar señales.

```http
GET /api/v1/rtv/processes/{processId}/latest/channel-categories
```

## Formato de respuesta

```json
{
  "channel_categorys": [
    {
      "channel_category_id": 2,
      "description": "Deportes"
    }
  ]
}
```

## Datos expuestos

| Campo | Tipo | Descripción |
|---|---|---|
| `channel_category_id` | entero | Identificador de la categoría del canal. |
| `description` | texto | Descripción de la categoría. |

## Consideraciones

- La raíz JSON se publica como `channel_categorys` para mantener compatibilidad con el contrato actual.

[Volver a la guía de clientes](../API_CLIENTES.md)
