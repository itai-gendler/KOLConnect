---
{
  "kind": "primary",
  "routes": {
    "offered": "Feishu Chat"
  },
  "steps": [
    {
      "text": "Request cancellation of the session's pending confirmation.",
      "kind": "actor",
      "actor": "feishu-chat-user",
      "entities": [],
      "contexts": {
        "offered": {
          "place": "feishu-chat-assistant"
        }
      }
    },
    {
      "text": "The session's pending confirmation is discarded and will not execute.",
      "kind": "product",
      "actor": "feishu-chat-user",
      "entities": [],
      "contexts": {
        "offered": {
          "place": "feishu-chat-assistant"
        }
      }
    }
  ],
  "references": [
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
      "target": "app/services/feishu_chat_transport.py"
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

# Pending confirmation discarded

## Trigger

Request cancellation of the session's pending confirmation.

## Outcome

The session's pending confirmation is discarded and will not execute.
