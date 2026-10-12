---
{
  "type": "messaging",
  "actors": [
    "feishu-chat-user"
  ],
  "languages": [
    "zh"
  ],
  "references": [
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
    }
  ]
}
---

# Feishu Chat Assistant

The optional official-SDK long connection receives bounded textual requests. Group messages require a bot mention; the assistant supports redacted reads and scoped confirmation of shipped operations.
