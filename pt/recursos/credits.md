---
title: "Créditos"
description: "Pessoas e créditos artísticos referenciados pelo conteúdo."
lang: pt
translation_path: "recursos/credits.html"
---

# Créditos

Pessoas e créditos artísticos referenciados pelo conteúdo.

```http
GET /api/v1/rtv/processes/{processId}/latest/credits
```

## Formato da resposta

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

## Dados expostos

| Campo | Tipo | Descrição |
|---|---|---|
| `type` | texto | Tipo de participação. |
| `id` | inteiro | Identificador da pessoa. |
| `name` | texto | Nome da pessoa. |
| `country` | inteiro | Identificador do país de origem. |
| `birth` | texto | Data de nascimento no formato `DD/MM/AAAA`. |
| `gender` | texto | Gênero informado. |
| `character` | texto | Personagem interpretado. |
| `images` | array | Imagens associadas ao crédito. |
| `images[].width` | inteiro | Largura da imagem em pixels. |
| `images[].height` | inteiro | Altura da imagem em pixels. |
| `images[].primary` | booleano | Indica se é a imagem principal. |
| `images[].url` | texto | URL pública da imagem. |

## Considerações

- `images` é incluído somente quando as imagens de créditos estão habilitadas para o processo.

[Voltar ao guia para clientes](../API_CLIENTES.md)
