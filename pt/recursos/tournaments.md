---
title: "Torneios"
description: "Torneios e competições esportivas disponíveis."
lang: pt
translation_path: "recursos/tournaments.html"
---

# Torneios

Torneios e competições esportivas disponíveis.

```http
GET /api/v1/rtv/processes/{processId}/latest/tournaments
```

## Formato da resposta

```json
{
  "tournaments": [
    {
      "id": 7,
      "name": "Torneo ejemplo",
      "description": "Descripción del torneo"
    }
  ]
}
```

## Dados expostos

| Campo | Tipo | Descrição |
|---|---|---|
| `id` | inteiro | Identificador do torneio. |
| `name` | texto | Nome do torneio. |
| `description` | texto | Descrição do torneio. |

[Voltar ao guia para clientes](../API_CLIENTES.md)
