---
title: "Países"
description: "Países referenciados pelos demais recursos."
lang: pt
translation_path: "recursos/countries.html"
---

# Países

Países referenciados pelos demais recursos.

```http
GET /api/v1/rtv/processes/{processId}/latest/countries
```

## Formato da resposta

```json
{
  "countries": [
    {
      "id": 32,
      "name": "Argentina",
      "gmt": "-03:00",
      "name_eng": "Argentina",
      "name_prt": "Argentina"
    }
  ]
}
```

## Dados expostos

| Campo | Tipo | Descrição |
|---|---|---|
| `id` | inteiro | Identificador do país. |
| `name` | texto | Nome do país. |
| `gmt` | texto | Diferença de horário informada. |
| `name_eng` | texto | Nome publicado no campo em inglês; atualmente replica `name`. |
| `name_prt` | texto | Nome publicado no campo em português; atualmente replica `name`. |

## Considerações

- `name_eng` e `name_prt` são incluídos quando os idiomas adicionais estão habilitados para o processo.

[Voltar ao guia para clientes](../API_CLIENTES.md)
