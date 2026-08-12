---
title: "Subgéneros"
description: "Subgéneros utilizados para clasificar el contenido."
lang: es
translation_path: "recursos/subgenres.html"
---

# Subgéneros

Subgéneros utilizados para clasificar el contenido.

```http
GET /api/v1/rtv/processes/{processId}/latest/subgenres
```

## Formato de respuesta

```json
{
  "subgenres": [
    {
      "id": 12,
      "name": "Fútbol",
      "name_eng": "Football",
      "name_prt": "Futebol"
    }
  ]
}
```

## Datos expuestos

| Campo | Tipo | Descripción |
|---|---|---|
| `id` | entero | Identificador del subgénero. |
| `name` | texto | Nombre en español. |
| `name_eng` | texto | Nombre en inglés. |
| `name_prt` | texto | Nombre en portugués. |

## Consideraciones

- `name_eng` y `name_prt` se incluyen cuando el proceso tiene habilitados los idiomas adicionales.

[Volver a la guía de clientes](../API_CLIENTES.md)
