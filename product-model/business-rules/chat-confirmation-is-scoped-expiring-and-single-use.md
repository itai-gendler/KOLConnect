---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "create-capture-task",
      "contexts": [
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
          "place": "feishu-chat-assistant"
        }
      ]
    },
    {
      "type": "capability",
      "id": "cancel-pending-assistant-operation",
      "contexts": [
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
      "target": "webapp/app.js"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/http_handlers/task_handler.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/services/task_service.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/adapters/task_manager_adapter.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/repositories/task_repository.py"
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
    },
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
    }
  ]
}
---

# Chat confirmation is scoped, expiring and single-use

Confirmation binds session, operation and arguments, expires after three hundred seconds and is single-use. It is consumed before execution, so failed execution requires a fresh preview/confirmation.
