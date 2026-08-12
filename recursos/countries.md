---
title: "Países"
description: "Países referenciados por los demás recursos."
lang: es
translation_path: "recursos/countries.html"
---

# Países

Países referenciados por los demás recursos.

```http
GET /api/v1/rtv/processes/{processId}/latest/countries
```

## Formato de respuesta

```json
{
  "countries": [
    {
      "id": 32,
      "name": "Argentina",
      "gmt": "-03:00",
      "name_eng": "Argentina",
      "name_prt": "Argentina"
    }
  ]
}
```

## Datos expuestos

| Campo | Tipo | Descripción |
|---|---|---|
| `id` | entero | Identificador del país. |
| `name` | texto | Nombre del país. |
| `gmt` | texto | Diferencia horaria informada. |
| `name_eng` | texto | Nombre publicado en el campo inglés; actualmente replica `name`. |
| `name_prt` | texto | Nombre publicado en el campo portugués; actualmente replica `name`. |

## Consideraciones

- `name_eng` y `name_prt` se incluyen cuando el proceso tiene habilitados los idiomas adicionales.

[Volver a la guía de clientes](../API_CLIENTES.md)
