---
title: "Channel categories"
description: "Categories used to classify channels."
lang: en
translation_path: "recursos/channel-categories.html"
---

# Channel categories

Categories used to classify channels.

```http
GET /api/v1/rtv/processes/{processId}/latest/channel-categories
```

## Response format

```json
{
  "channel_categorys": [
    {
      "channel_category_id": 2,
      "description": "Deportes"
    }
  ]
}
```

## Exposed data

| Field | Type | Description |
|---|---|---|
| `channel_category_id` | integer | Channel category identifier. |
| `description` | string | Category description. |

## Considerations

- The JSON root is published as `channel_categorys` for compatibility with the current contract.

[Back to the client guide](../API_CLIENTES.md)
