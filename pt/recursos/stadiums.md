---
title: "Estádios"
description: "Estádios e locais esportivos disponíveis."
lang: pt
translation_path: "recursos/stadiums.html"
---

# Estádios

Estádios e locais esportivos disponíveis.

```http
GET /api/v1/rtv/processes/{processId}/latest/stadiums
```

## Formato da resposta

```json
{
  "stadiums": [
    {
      "id": 4,
      "name": "Estadio ejemplo",
      "location": "Buenos Aires"
    }
  ]
}
```

## Dados expostos

| Campo | Tipo | Descrição |
|---|---|---|
| `id` | inteiro | Identificador do estádio. |
| `name` | texto | Nome do estádio. |
| `location` | texto | Localização informada. |

[Voltar ao guia para clientes](../API_CLIENTES.md)
