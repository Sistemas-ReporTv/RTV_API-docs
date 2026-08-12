---
title: "Categorias"
description: "Categorias usadas para classificar o conteúdo."
lang: pt
translation_path: "recursos/categories.html"
---

# Categorias

Categorias usadas para classificar o conteúdo.

```http
GET /api/v1/rtv/processes/{processId}/latest/categories
```

## Formato da resposta

```json
{
  "categories": [
    {
      "id": 1,
      "name": "Películas",
      "name_eng": "Movies",
      "name_prt": "Filmes"
    }
  ]
}
```

## Dados expostos

| Campo | Tipo | Descrição |
|---|---|---|
| `id` | inteiro | Identificador da categoria. |
| `name` | texto | Nome em espanhol. |
| `name_eng` | texto | Nome em inglês. |
| `name_prt` | texto | Nome em português. |

## Considerações

- `name_eng` e `name_prt` são incluídos quando os idiomas adicionais estão habilitados para o processo.

[Voltar ao guia para clientes](../API_CLIENTES.md)
