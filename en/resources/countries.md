---
title: "Countries"
description: "Countries referenced by other resources."
lang: en
translation_path: "recursos/countries.html"
---

# Countries

Countries referenced by other resources.

```http
GET /api/v1/rtv/processes/{processId}/latest/countries
```

## Response format

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

## Exposed data

| Field | Type | Description |
|---|---|---|
| `id` | integer | Country identifier. |
| `name` | string | Country name. |
| `gmt` | string | Reported time offset. |
| `name_eng` | string | Name published in the English field; currently mirrors `name`. |
| `name_prt` | string | Name published in the Portuguese field; currently mirrors `name`. |

## Considerations

- `name_eng` and `name_prt` are included when additional languages are enabled for the process.

[Back to the client guide](../API_CLIENTES.md)
