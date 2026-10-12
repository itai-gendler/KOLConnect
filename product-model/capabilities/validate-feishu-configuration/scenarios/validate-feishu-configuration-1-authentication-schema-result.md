---
{
  "kind": "primary",
  "routes": {
    "offered": "Feishu Integration"
  },
  "steps": [
    {
      "text": "Request Feishu credential and schema validation.",
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
      "text": "Supported Feishu authentication and table/schema compatibility results are returned.",
      "kind": "product",
      "actor": "local-user",
      "entities": [
        {
          "entity": "feishu-settings",
          "effect": "reads",
          "facts": [
            "Connector identifiers",
            "Protected secret",
            "Target tables",
            "Chat enabled",
            "Configuration status",
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
    }
  ]
}
---

# Authentication/schema result

## Trigger

Request Feishu credential and schema validation.

## Outcome

Supported Feishu authentication and table/schema compatibility results are returned.
