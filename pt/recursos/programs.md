---
title: "Programas"
description: "Programas e seus metadados editoriais."
lang: pt
translation_path: "recursos/programs.html"
---

# Programas

Programas e seus metadados editoriais.

```http
GET /api/v1/rtv/processes/{processId}/latest/programs
```

## Formato da resposta

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

## Dados expostos

| Campo | Tipo | Descrição |
|---|---|---|
| `id` | inteiro | Identificador do programa. |
| `imdb_id` | texto | Identificador do IMDb, quando habilitado e disponível. |
| `imdb_rating` | número | Nota do IMDb, maior que 0 e até 10, quando habilitada e disponível. |
| `sport_event` | booleano | Indica se é um evento esportivo. |
| `main_title` | texto | Título principal. |
| `original_title` | texto | Título original. |
| `long_argument` | objeto | Sinopse longa em espanhol (`lang` e `value`). |
| `short_argument` | objeto | Sinopse curta em espanhol (`lang` e `value`). |
| `year` | inteiro | Ano do conteúdo. |
| `parental_rating` | objeto | Classificação indicativa: `type` e `value`. |
| `long_description` | objeto | Descrição longa em inglês (`lang` e `value`). |
| `short_description` | objeto | Descrição curta em inglês (`lang` e `value`). |
| `images` | array | Imagens do programa. |
| `images[].width` | inteiro | Largura em pixels. |
| `images[].height` | inteiro | Altura em pixels. |
| `images[].primary` | booleano | Indica se é o principal. |
| `images[].url` | texto | Referência da imagem conforme a modalidade de entrega acordada; veja [entrega de imagens](../API_CLIENTES.md). |
| `images[].poster` | booleano | Indica se o formato corresponde a pôster. |
| `keywords` | array de textos | Palavras-chave associadas. |
| `related_programs` | array | Programas relacionados. |
| `related_programs[].type_id` | inteiro | Tipo de relação. |
| `related_programs[].program_id` | inteiro | Programa relacionado. |
| `references` | array | Referências a categoria, gênero, subgênero, atores, diretores e país. |
| `references[].type` | texto | Tipo de referência. |
| `references[].id` | inteiro ou texto | Identificador ou lista de identificadores. |

## Considerações

- `imdb_id` e `imdb_rating` são opcionais e podem ser omitidos de forma independente conforme a configuração e os dados disponíveis.
- `poster` é incluído quando o processo habilita esse atributo.
- Com idiomas adicionais, são adicionados: `main_title_eng`, `main_title_prt`, `original_title_eng`, `original_title_prt`, `long_argument_prt` e `short_argument_prt`.

[Voltar ao guia para clientes](../API_CLIENTES.md)
