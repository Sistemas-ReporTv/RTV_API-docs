# Créditos

Personas y créditos artísticos referenciados por el contenido.

```http
GET /api/v1/rtv/processes/{processId}/latest/credits
```

## Formato de respuesta

```json
{
  "credits": [
    {
      "type": "Actor",
      "id": 45,
      "name": "Persona ejemplo",
      "country": 32,
      "birth": "15/04/1980",
      "gender": "F",
      "character": "Personaje",
      "images": [
        {
          "width": 300,
          "height": 450,
          "primary": true,
          "url": "https://imagenes.ejemplo.com/45.jpg"
        }
      ]
    }
  ]
}
```

## Datos expuestos

| Campo | Tipo | Descripción |
|---|---|---|
| `type` | texto | Tipo de participación. |
| `id` | entero | Identificador de la persona. |
| `name` | texto | Nombre de la persona. |
| `country` | entero | Identificador del país de origen. |
| `birth` | texto | Fecha de nacimiento con formato `DD/MM/AAAA`. |
| `gender` | texto | Género informado. |
| `character` | texto | Personaje interpretado. |
| `images` | arreglo | Imágenes asociadas al crédito. |
| `images[].width` | entero | Ancho de la imagen en píxeles. |
| `images[].height` | entero | Alto de la imagen en píxeles. |
| `images[].primary` | booleano | Indica si es la imagen principal. |
| `images[].url` | texto | URL pública de la imagen. |

## Consideraciones

- `images` se incluye únicamente cuando las imágenes de créditos están habilitadas para el proceso.

[Volver a la guía de clientes](../API_CLIENTES.md)
