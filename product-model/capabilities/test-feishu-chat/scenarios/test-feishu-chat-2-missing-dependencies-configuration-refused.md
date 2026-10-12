---
{
  "kind": "validation",
  "routes": {
    "offered": "Feishu Integration"
  },
  "steps": [
    {
      "text": "Request a local Chat configuration and SDK check.",
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
      "text": "Missing configuration or SDK dependencies are reported and no transport is opened.",
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

# Missing dependencies/configuration refused

## Trigger

Request a local Chat configuration and SDK check.

## Outcome

Missing configuration or SDK dependencies are reported and no transport is opened.
