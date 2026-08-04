# Episodios

Episodios o capítulos asociados a los programas.

```http
GET /api/v1/rtv/processes/{processId}/latest/episodes
```

## Formato de respuesta

```json
{
  "episodes": [
    {
      "id": 2001,
      "program_id": 1001,
      "title": "Episodio ejemplo",
      "number": 1,
      "season_id": 3001,
      "long_argument": {
        "lang": "spa",
        "value": "Sinopsis"
      },
      "short_argument": {
        "lang": "spa",
        "value": "Resumen"
      },
      "long_description": {
        "lang": "eng",
        "value": "Synopsis"
      },
      "short_description": {
        "lang": "eng",
        "value": "Summary"
      },
      "references": [
        {
          "type": "actor",
          "id": "45,46"
        }
      ],
      "images": [
        {
          "width": 600,
          "height": 400,
          "primary": true,
          "url": "https://imagenes.ejemplo.com/2001.jpg"
        }
      ]
    }
  ]
}
```

## Datos expuestos

| Campo | Tipo | Descripción |
|---|---|---|
| `id` | entero | Identificador del episodio. |
| `program_id` | entero | Identificador del programa. |
| `title` | texto | Título oficial. |
| `number` | entero | Número de episodio. |
| `season_id` | entero | Identificador de temporada. |
| `long_argument` | objeto | Sinopsis larga en español (`lang` y `value`). |
| `short_argument` | objeto | Sinopsis corta en español (`lang` y `value`). |
| `long_description` | objeto | Descripción larga en inglés (`lang` y `value`). |
| `short_description` | objeto | Descripción corta en inglés (`lang` y `value`). |
| `references` | arreglo | Referencias a actores y directores. |
| `references[].type` | texto | Tipo de referencia. |
| `references[].id` | texto | Identificadores separados por coma. |
| `images` | arreglo | Imágenes del episodio. |
| `images[].width` | entero | Ancho de la imagen en píxeles. |
| `images[].height` | entero | Alto de la imagen en píxeles. |
| `images[].primary` | booleano | Indica si es la imagen principal. |
| `images[].url` | texto | URL pública de la imagen. |

## Consideraciones

- Con idiomas adicionales se agregan `title_eng`, `title_prt`, `long_argument_prt` y `short_argument_prt`.
- Para eventos deportivos se agrega `sportDetail` con `tournament`, `year`, `sport`, `stadium`, `round`, `team1`, `team2` y `statistics`.

[Volver a la guía de clientes](../API_CLIENTES.md)
