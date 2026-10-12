---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "change-integration-settings",
      "contexts": [
        {
          "place": "kolconnect-desktop::feishu-integration"
        },
        {
          "place": "kolconnect-desktop::google-sheets-integration"
        }
      ]
    },
    {
      "type": "entity",
      "id": "feishu-settings",
      "effect": "changes",
      "facts": [
        "Protected secret"
      ],
      "contexts": [
        {
          "place": "kolconnect-desktop::feishu-integration"
        }
      ]
    },
    {
      "type": "entity",
      "id": "google-sheets-settings",
      "effect": "changes",
      "facts": [
        "Client configuration"
      ],
      "contexts": [
        {
          "place": "kolconnect-desktop::google-sheets-integration"
        }
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

# Masked connector saves preserve existing secrets

Masked Feishu/Google configuration values preserve existing secrets through the supported save policy. Protected secret values are not echoed into conversational disclosure.
