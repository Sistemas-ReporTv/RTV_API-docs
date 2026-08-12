---
title: "Equipes"
description: "Equipes esportivas disponíveis para o processo."
lang: pt
translation_path: "recursos/teams.html"
---

# Equipes

Equipes esportivas disponíveis para o processo.

```http
GET /api/v1/rtv/processes/{processId}/latest/teams
```

## Formato da resposta

```json
{
  "teams": [
    {
      "id": 10,
      "name": "Equipo ejemplo",
      "stadium_id": 4,
      "county_id": 32
    }
  ]
}
```

## Dados expostos

| Campo | Tipo | Descrição |
|---|---|---|
| `id` | inteiro | Identificador da equipe. |
| `name` | texto | Nome da equipe. |
| `stadium_id` | inteiro | Identificador do estádio associado. |
| `county_id` | inteiro | Identificador do país. O nome histórico é mantido por compatibilidade. |

[Voltar ao guia para clientes](../API_CLIENTES.md)
