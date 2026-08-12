---
title: "Prêmios"
description: "Catálogo de prêmios disponível."
lang: pt
translation_path: "recursos/awards.html"
---

# Prêmios

Catálogo de prêmios disponível.

```http
GET /api/v1/rtv/processes/{processId}/latest/awards
```

## Formato da resposta

```json
{
  "awards": [
    {
      "id": 3,
      "value": "Premio ejemplo"
    }
  ]
}
```

## Dados expostos

| Campo | Tipo | Descrição |
|---|---|---|
| `id` | inteiro | Identificador do prêmio. |
| `value` | texto | Descrição ou nome do prêmio. |

[Voltar ao guia para clientes](../API_CLIENTES.md)
