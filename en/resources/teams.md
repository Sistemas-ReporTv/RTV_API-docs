---
title: "Teams"
description: "Sports teams available to the process."
lang: en
translation_path: "recursos/teams.html"
---

# Teams

Sports teams available to the process.

```http
GET /api/v1/rtv/processes/{processId}/latest/teams
```

## Response format

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

## Exposed data

| Field | Type | Description |
|---|---|---|
| `id` | integer | Team identifier. |
| `name` | string | Team name. |
| `stadium_id` | integer | Associated stadium identifier. |
| `county_id` | integer | Country identifier. The historical name is retained for compatibility. |

[Back to the client guide](../API_CLIENTES.md)
