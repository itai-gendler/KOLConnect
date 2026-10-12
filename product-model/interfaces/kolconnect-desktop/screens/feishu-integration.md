---
{
  "entities": [
    {
      "entity": "feishu-settings",
      "shows": [
        "Connector identifiers",
        "Protected secret",
        "Target tables",
        "Chat enabled",
        "Configuration status",
        "Transport status"
      ],
      "collects": [
        "Connector identifiers",
        "Protected secret",
        "Target tables",
        "Chat enabled"
      ]
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
    }
  ]
}
---

# Feishu Integration

Connector configuration, validation, sync plan/outcome and Chat transport status

 settings and confirmations.
