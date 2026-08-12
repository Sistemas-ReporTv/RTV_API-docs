---
title: "Subgêneros"
description: "Subgêneros usados para classificar o conteúdo."
lang: pt
translation_path: "recursos/subgenres.html"
---

# Subgêneros

Subgêneros usados para classificar o conteúdo.

```http
GET /api/v1/rtv/processes/{processId}/latest/subgenres
```

## Formato da resposta

```json
{
  "subgenres": [
    {
      "id": 12,
      "name": "Fútbol",
      "name_eng": "Football",
      "name_prt": "Futebol"
    }
  ]
}
```

## Dados expostos

| Campo | Tipo | Descrição |
|---|---|---|
| `id` | inteiro | Identificador do subgênero. |
| `name` | texto | Nome em espanhol. |
| `name_eng` | texto | Nome em inglês. |
| `name_prt` | texto | Nome em português. |

## Considerações

- `name_eng` e `name_prt` são incluídos quando os idiomas adicionais estão habilitados para o processo.

[Voltar ao guia para clientes](../API_CLIENTES.md)
