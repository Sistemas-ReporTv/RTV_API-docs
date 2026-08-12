---
title: "Temporadas"
description: "Temporadas associadas aos programas."
lang: pt
translation_path: "recursos/seasons.html"
---

# Temporadas

Temporadas associadas aos programas.

```http
GET /api/v1/rtv/processes/{processId}/latest/seasons
```

## Formato da resposta

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

## Dados expostos

| Campo | Tipo | Descrição |
|---|---|---|
| `id` | inteiro | Identificador da temporada. |
| `title` | texto | Título ou descrição. |
| `number` | inteiro | Número da temporada. |
| `argument` | texto | Sinopse da temporada. |
| `references` | array | Referências a atores e diretores. |
| `references[].type` | texto | Tipo de referência. |
| `references[].id` | texto | Identificadores separados por vírgula. |
| `images` | array | Imagens da temporada. |
| `images[].width` | inteiro | Largura da imagem em pixels. |
| `images[].height` | inteiro | Altura da imagem em pixels. |
| `images[].primary` | booleano | Indica se é a imagem principal. |
| `images[].url` | texto | URL pública da imagem. |

## Considerações

- Com idiomas adicionais, são adicionados: `title_eng`, `title_prt`, `argument_eng` e `argument_prt`.

[Voltar ao guia para clientes](../API_CLIENTES.md)
