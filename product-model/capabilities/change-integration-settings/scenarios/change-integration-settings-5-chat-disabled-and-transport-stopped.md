---
{
  "kind": "primary",
  "routes": {
    "offered": "Feishu Integration"
  },
  "steps": [
    {
      "text": "Supply selected integration settings or change the optional Chat switch.",
      "kind": "actor",
      "actor": "local-user",
      "entities": [],
      "contexts": {
        "offered": {
          "place": "kolconnect-desktop::feishu-integration"
        }
      }
    },
    {
      "text": "The Chat enabled flag is cleared and the transport is stopped.",
      "kind": "product",
      "actor": "local-user",
      "entities": [
        {
          "entity": "feishu-settings",
          "effect": "changes",
          "facts": [
            "Chat enabled",
            "Transport status"
          ]
        }
      ],
      "contexts": {
        "offered": {
          "place": "kolconnect-desktop::feishu-integration"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "webapp/pages/settings.js"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/services/feishu_sync_service.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/http_handlers/feishu_sync_handler.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/services/feishu_chat_transport.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/services/feishu_chat_service.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/http_handlers/google_sheets_handler.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/services/google_sheets_data_sync_service.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/google_sheets_client.py"
    }
  ]
}
---

# Chat disabled and transport stopped

## Trigger

Supply selected integration settings or change the optional Chat switch.

## Outcome

The Chat enabled flag is cleared and the transport is stopped.
