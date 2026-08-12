---
title: "Tipos de relação entre programas"
description: "Tipos usados para relacionar programas entre si."
lang: pt
translation_path: "recursos/related-program-types.html"
---

# Tipos de relação entre programas

Tipos usados para relacionar programas entre si.

```http
GET /api/v1/rtv/processes/{processId}/latest/related-program-types
```

## Formato da resposta

```json
{
  "related_program_types": [
    {
      "relation_type_id": 1,
      "value": "Relacionado"
    }
  ]
}
```

## Dados expostos

| Campo | Tipo | Descrição |
|---|---|---|
| `relation_type_id` | inteiro | Identificador do tipo de relação. |
| `value` | texto | Descrição do tipo de relação. |

[Voltar ao guia para clientes](../API_CLIENTES.md)
