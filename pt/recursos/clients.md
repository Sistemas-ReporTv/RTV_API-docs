---
title: "Clientes"
description: "Clientes habilitados no feed."
lang: pt
translation_path: "recursos/clients.html"
---

# Clientes

Clientes habilitados no feed.

```http
GET /api/v1/rtv/processes/{processId}/latest/clients
```

## Formato da resposta

```json
{
  "clients": [
    {
      "id": 123,
      "name": "Cliente ejemplo",
      "country_id": 32
    }
  ]
}
```

## Dados expostos

| Campo | Tipo | Descrição |
|---|---|---|
| `id` | inteiro | Identificador do cliente. |
| `name` | texto | Razão social ou nome. |
| `country_id` | inteiro | Identificador do país. |

[Voltar ao guia para clientes](../API_CLIENTES.md)
