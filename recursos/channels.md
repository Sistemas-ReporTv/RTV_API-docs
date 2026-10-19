---
title: "Canales"
description: "Señales o canales incluidos en el proceso."
lang: es
translation_path: "recursos/channels.html"
---

# Canales

Señales o canales incluidos en el proceso.

```http
GET /api/v1/rtv/processes/{processId}/latest/channels
```

## Formato de respuesta

```json
{
  "channels": [
    {
      "id": 15,
      "name": "Canal ejemplo",
      "country_id": 32,
      "channel_category_id": 2,
      "alternative_name": "CEX",
      "sintony": 101,
      "hd": true,
      "logos": [
        {
          "width": 400,
          "height": 200,
          "url": "https://imagenes.ejemplo.com/100.jpg"
        }
      ]
    }
  ]
}
```

## Datos expuestos

| Campo | Tipo | Descripción |
|---|---|---|
| `id` | entero | Identificador del canal. |
| `name` | texto | Nombre del canal. |
| `country_id` | entero | Identificador del país. |
| `channel_category_id` | entero | Identificador de la categoría del canal. |
| `alternative_name` | texto | Nombre corto o abreviatura. |
| `sintony` | entero | Número de sintonía. |
| `hd` | booleano | Indica si la señal es HD. |
| `logos` | arreglo | Logos disponibles para el canal. |
| `logos[].width` | entero | Ancho de la imagen en píxeles. |
| `logos[].height` | entero | Alto de la imagen en píxeles. |
| `logos[].url` | texto | Referencia de la imagen según la modalidad de entrega acordada; ver [entrega de imágenes](../API_CLIENTES.md). |

## Consideraciones

- El nombre puede normalizarse según la configuración del proceso.

[Volver a la guía de clientes](../API_CLIENTES.md)
