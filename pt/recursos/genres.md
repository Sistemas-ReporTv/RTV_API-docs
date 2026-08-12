---
title: "Gêneros"
description: "Gêneros usados para classificar o conteúdo."
lang: pt
translation_path: "recursos/genres.html"
---

# Gêneros

Gêneros usados para classificar o conteúdo.

```http
GET /api/v1/rtv/processes/{processId}/latest/genres
```

## Formato da resposta

```json
{
  "genres": [
    {
      "id": 5,
      "name": "Deportes",
      "name_eng": "Sports",
      "name_prt": "Esportes"
    }
  ]
}
```

## Dados expostos

| Campo | Tipo | Descrição |
|---|---|---|
| `id` | inteiro | Identificador do gênero. |
| `name` | texto | Nome em espanhol. |
| `name_eng` | texto | Nome em inglês. |
| `name_prt` | texto | Nome em português. |

## Considerações

- `name_eng` e `name_prt` são incluídos quando os idiomas adicionais estão habilitados.
- Os identificadores e nomes podem corresponder ao catálogo de gêneros equivalentes configurado para o processo.

[Voltar ao guia para clientes](../API_CLIENTES.md)
