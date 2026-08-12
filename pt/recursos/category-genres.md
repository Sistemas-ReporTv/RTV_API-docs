---
title: "Relações entre categorias e gêneros"
description: "Associações válidas entre categorias e gêneros."
lang: pt
translation_path: "recursos/category-genres.html"
---

# Relações entre categorias e gêneros

Associações válidas entre categorias e gêneros.

```http
GET /api/v1/rtv/processes/{processId}/latest/category-genres
```

## Formato da resposta

```json
{
  "categories_genres": [
    {
      "category_id": 1,
      "genre_id": 5
    }
  ]
}
```

## Dados expostos

| Campo | Tipo | Descrição |
|---|---|---|
| `category_id` | inteiro | Identificador da categoria. |
| `genre_id` | inteiro | Identificador do gênero. |

## Considerações

- `genre_id` pode usar o catálogo de gêneros equivalentes configurado para o processo.

[Voltar ao guia para clientes](../API_CLIENTES.md)
