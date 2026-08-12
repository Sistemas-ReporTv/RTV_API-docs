---
title: "Canais"
description: "Sinais ou canais incluídos no processo."
lang: pt
translation_path: "recursos/channels.html"
---

# Canais

Sinais ou canais incluídos no processo.

```http
GET /api/v1/rtv/processes/{processId}/latest/channels
```

## Formato da resposta

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

## Dados expostos

| Campo | Tipo | Descrição |
|---|---|---|
| `id` | inteiro | Identificador do canal. |
| `name` | texto | Nome do canal. |
| `country_id` | inteiro | Identificador do país. |
| `channel_category_id` | inteiro | Identificador da categoria do canal. |
| `alternative_name` | texto | Nome curto ou abreviação. |
| `sintony` | inteiro | Número de sintonia. |
| `hd` | booleano | Indica se o sinal é HD. |
| `logos` | array | Logotipos disponíveis para o canal. |
| `logos[].width` | inteiro | Largura da imagem em pixels. |
| `logos[].height` | inteiro | Altura da imagem em pixels. |
| `logos[].url` | texto | URL pública da imagem. |

## Considerações

- O nome pode ser normalizado conforme a configuração do processo.

[Voltar ao guia para clientes](../API_CLIENTES.md)
