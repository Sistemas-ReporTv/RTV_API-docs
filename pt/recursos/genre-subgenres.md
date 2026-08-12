---
title: "Relações entre gêneros e subgêneros"
description: "Associações válidas entre gêneros e subgêneros."
lang: pt
translation_path: "recursos/genre-subgenres.html"
---

# Relações entre gêneros e subgêneros

Associações válidas entre gêneros e subgêneros.

```http
GET /api/v1/rtv/processes/{processId}/latest/genre-subgenres
```

## Formato da resposta

```json
{
  "genres_subgenres": [
    {
      "genre_id": 5,
      "subgenre_id": 12
    }
  ]
}
```

## Dados expostos

| Campo | Tipo | Descrição |
|---|---|---|
| `genre_id` | inteiro | Identificador do gênero. |
| `subgenre_id` | inteiro | Identificador do subgênero. |

## Considerações

- `genre_id` pode usar o catálogo de gêneros equivalentes configurado para o processo.

[Voltar ao guia para clientes](../API_CLIENTES.md)
