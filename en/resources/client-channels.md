---
title: "Channels by client"
description: "Channels associated with each client."
lang: en
translation_path: "recursos/client-channels.html"
---

# Channels by client

Channels associated with each client.

```http
GET /api/v1/rtv/processes/{processId}/latest/client-channels
```

## Response format

```json
{
  "client_channels": [
    {
      "client_id": 123,
      "channel_id": 15,
      "channel": 101,
      "short_name": "CEX",
      "name": "Canal ejemplo",
      "alignment_id": 2
    }
  ]
}
```

## Exposed data

| Field | Type | Description |
|---|---|---|
| `client_id` | integer | Client identifier. |
| `channel_id` | integer | Channel identifier. |
| `channel` | integer | Assigned channel number. |
| `short_name` | string | Short channel name. |
| `name` | string | Channel name. |
| `alignment_id` | integer | Lineup identifier. |

[Back to the client guide](../API_CLIENTES.md)
