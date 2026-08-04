# Programas

Programas y sus metadatos editoriales.

```http
GET /api/v1/rtv/processes/{processId}/latest/programs
```

## Formato de respuesta

```json
{
  "programs": [
    {
      "id": 1001,
      "sport_event": false,
      "main_title": "Programa ejemplo",
      "original_title": "Original title",
      "long_argument": {
        "lang": "spa",
        "value": "Descripción extensa"
      },
      "short_argument": {
        "lang": "spa",
        "value": "Descripción breve"
      },
      "year": 2026,
      "parental_rating": {
        "type": "VCHIP",
        "value": "ATP"
      },
      "long_description": {
        "lang": "eng",
        "value": "Long description"
      },
      "short_description": {
        "lang": "eng",
        "value": "Short description"
      },
      "images": [
        {
          "width": 600,
          "height": 900,
          "primary": true,
          "url": "https://imagenes.ejemplo.com/1001.jpg",
          "poster": true
        }
      ],
      "keywords": [
        "ejemplo"
      ],
      "related_programs": [
        {
          "type_id": 1,
          "program_id": 1002
        }
      ],
      "references": [
        {
          "type": "category",
          "id": 1
        },
        {
          "type": "genre",
          "id": 5
        }
      ]
    }
  ]
}
```

## Datos expuestos

| Campo | Tipo | Descripción |
|---|---|---|
| `id` | entero | Identificador del programa. |
| `sport_event` | booleano | Indica si es un evento deportivo. |
| `main_title` | texto | Título principal. |
| `original_title` | texto | Título original. |
| `long_argument` | objeto | Sinopsis larga en español (`lang` y `value`). |
| `short_argument` | objeto | Sinopsis corta en español (`lang` y `value`). |
| `year` | entero | Año del contenido. |
| `parental_rating` | objeto | Clasificación parental: `type` y `value`. |
| `long_description` | objeto | Descripción larga en inglés (`lang` y `value`). |
| `short_description` | objeto | Descripción corta en inglés (`lang` y `value`). |
| `images` | arreglo | Imágenes del programa. |
| `images[].width` | entero | Ancho en píxeles. |
| `images[].height` | entero | Alto en píxeles. |
| `images[].primary` | booleano | Indica si es principal. |
| `images[].url` | texto | URL pública. |
| `images[].poster` | booleano | Indica si el formato corresponde a póster. |
| `keywords` | arreglo de textos | Palabras clave asociadas. |
| `related_programs` | arreglo | Programas relacionados. |
| `related_programs[].type_id` | entero | Tipo de relación. |
| `related_programs[].program_id` | entero | Programa relacionado. |
| `references` | arreglo | Referencias a categoría, género, subgénero, actores, directores y país. |
| `references[].type` | texto | Tipo de referencia. |
| `references[].id` | entero o texto | Identificador o lista de identificadores. |

## Consideraciones

- `poster` se incluye cuando el proceso habilita ese atributo.
- Con idiomas adicionales se agregan `main_title_eng`, `main_title_prt`, `original_title_eng`, `original_title_prt`, `long_argument_prt` y `short_argument_prt`.

[Volver a la guía de clientes](../API_CLIENTES.md)
