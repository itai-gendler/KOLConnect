---
{
  "appliesTo": [
    {
      "type": "context",
      "context": {
        "place": "feishu-chat-assistant"
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

# Chat scope, mentions and replay protection constrain processing

Feishu processing scopes p2p sessions to chat and group sessions to chat/sender; groups require a bot mention. Duplicate event/message suppression is bounded to six hundred seconds/two thousand forty-eight entries. Only textual requests use the shipped conversational contract.
