---
title: "Episódios"
description: "Episódios ou capítulos associados aos programas."
lang: pt
translation_path: "recursos/episodes.html"
---

# Episódios

Episódios ou capítulos associados aos programas.

```http
GET /api/v1/rtv/processes/{processId}/latest/episodes
```

## Formato da resposta

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

## Dados expostos

| Campo | Tipo | Descrição |
|---|---|---|
| `id` | inteiro | Identificador do episódio. |
| `program_id` | inteiro | Identificador do programa. |
| `title` | texto | Título oficial. |
| `number` | inteiro | Número do episódio. |
| `season_id` | inteiro | Identificador da temporada. |
| `long_argument` | objeto | Sinopse longa em espanhol (`lang` e `value`). |
| `short_argument` | objeto | Sinopse curta em espanhol (`lang` e `value`). |
| `long_description` | objeto | Descrição longa em inglês (`lang` e `value`). |
| `short_description` | objeto | Descrição curta em inglês (`lang` e `value`). |
| `references` | array | Referências a atores e diretores. |
| `references[].type` | texto | Tipo de referência. |
| `references[].id` | texto | Identificadores separados por vírgula. |
| `images` | array | Imagens do episódio. |
| `images[].width` | inteiro | Largura da imagem em pixels. |
| `images[].height` | inteiro | Altura da imagem em pixels. |
| `images[].primary` | booleano | Indica se é a imagem principal. |
| `images[].url` | texto | URL pública da imagem. |

## Considerações

- Com idiomas adicionais, são adicionados: `title_eng`, `title_prt`, `long_argument_prt` e `short_argument_prt`.
- Para eventos esportivos, é adicionado: `sportDetail` con `tournament`, `year`, `sport`, `stadium`, `round`, `team1`, `team2` e `statistics`.

[Voltar ao guia para clientes](../API_CLIENTES.md)
