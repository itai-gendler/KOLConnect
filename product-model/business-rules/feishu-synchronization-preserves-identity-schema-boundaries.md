---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "validate-feishu-configuration",
      "contexts": [
        {
          "place": "kolconnect-desktop::feishu-integration"
        }
      ]
    },
    {
      "type": "capability",
      "id": "preview-feishu-sync",
      "contexts": [
        {
          "place": "kolconnect-desktop::feishu-integration"
        },
        {
          "place": "feishu-chat-assistant"
        }
      ]
    },
    {
      "type": "capability",
      "id": "run-feishu-sync",
      "contexts": [
        {
          "place": "kolconnect-desktop::feishu-integration"
        },
        {
          "place": "feishu-chat-assistant"
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
      "target": "app/services/feishu_chat_message_adapter.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/services/assistant_service.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/services/assistant_confirmation_store.py"
    }
  ]
}
---

# Feishu synchronization preserves identity/schema boundaries

Feishu synchronization validates required schema, account/canonical identities and relation boundaries before executable writes. Conflicting or ambiguous plans prevent execution.
