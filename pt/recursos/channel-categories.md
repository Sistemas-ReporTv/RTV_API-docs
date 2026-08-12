---
title: "Categorias de canais"
description: "Categorias usadas para classificar sinais."
lang: pt
translation_path: "recursos/channel-categories.html"
---

# Categorias de canais

Categorias usadas para classificar sinais.

```http
GET /api/v1/rtv/processes/{processId}/latest/channel-categories
```

## Formato da resposta

```json
{
  "channel_categorys": [
    {
      "channel_category_id": 2,
      "description": "Deportes"
    }
  ]
}
```

## Dados expostos

| Campo | Tipo | Descrição |
|---|---|---|
| `channel_category_id` | inteiro | Identificador da categoria do canal. |
| `description` | texto | Descrição da categoria. |

## Considerações

- A raiz JSON é publicada como `channel_categorys` para manter a compatibilidade com o contrato atual.

[Voltar ao guia para clientes](../API_CLIENTES.md)
