---
title: "Canais por cliente"
description: "Canais associados a cada cliente."
lang: pt
translation_path: "recursos/client-channels.html"
---

# Canais por cliente

Canais associados a cada cliente.

```http
GET /api/v1/rtv/processes/{processId}/latest/client-channels
```

## Formato da resposta

```json
{
  "client_channels": [
    {
      "client_id": 123,
      "channel_id": 15,
      "channel": 101,
      "short_name": "CEX",
      "name": "Canal ejemplo",
      "alignment_id": 2
    }
  ]
}
```

## Dados expostos

| Campo | Tipo | Descrição |
|---|---|---|
| `client_id` | inteiro | Identificador do cliente. |
| `channel_id` | inteiro | Identificador do canal. |
| `channel` | inteiro | Número de canal atribuído. |
| `short_name` | texto | Nome curto do canal. |
| `name` | texto | Nome do canal. |
| `alignment_id` | inteiro | Identificador do alinhamento. |

[Voltar ao guia para clientes](../API_CLIENTES.md)
