---
title: "Temporadas"
description: "Temporadas asociadas a los programas."
lang: es
translation_path: "recursos/seasons.html"
---

# Temporadas

Temporadas asociadas a los programas.

```http
GET /api/v1/rtv/processes/{processId}/latest/seasons
```

## Formato de respuesta

```json
{
  "seasons": [
    {
      "id": 3001,
      "title": "Temporada 1",
      "number": 1,
      "argument": "Descripción de la temporada",
      "references": [
        {
          "type": "director",
          "id": "50"
        }
      ],
      "images": [
        {
          "width": 600,
          "height": 900,
          "primary": true,
          "url": "https://imagenes.ejemplo.com/3001.jpg"
        }
      ]
    }
  ]
}
```

## Datos expuestos

| Campo | Tipo | Descripción |
|---|---|---|
| `id` | entero | Identificador de la temporada. |
| `title` | texto | Título o descripción. |
| `number` | entero | Número de temporada. |
| `argument` | texto | Sinopsis de la temporada. |
| `references` | arreglo | Referencias a actores y directores. |
| `references[].type` | texto | Tipo de referencia. |
| `references[].id` | texto | Identificadores separados por coma. |
| `images` | arreglo | Imágenes de la temporada. |
| `images[].width` | entero | Ancho de la imagen en píxeles. |
| `images[].height` | entero | Alto de la imagen en píxeles. |
| `images[].primary` | booleano | Indica si es la imagen principal. |
| `images[].url` | texto | URL pública de la imagen. |

## Consideraciones

- Con idiomas adicionales se agregan `title_eng`, `title_prt`, `argument_eng` y `argument_prt`.

[Volver a la guía de clientes](../API_CLIENTES.md)
