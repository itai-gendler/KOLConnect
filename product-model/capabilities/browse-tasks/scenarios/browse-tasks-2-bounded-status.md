---
{
  "kind": "primary",
  "routes": {
    "offered": "Feishu Chat"
  },
  "steps": [
    {
      "text": "Request the work inventory or status of the selected capture work.",
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
      "text": "Chat returns bounded status for the addressed existing task.",
      "kind": "product",
      "actor": "feishu-chat-user",
      "entities": [
        {
          "entity": "capture-task",
          "effect": "reads",
          "facts": [
            "Task identity",
            "Name",
            "Lifecycle",
            "Progress"
          ]
        },
        {
          "entity": "manual-task",
          "effect": "reads",
          "facts": [
            "Task identity",
            "Name",
            "Lifecycle",
            "Progress"
          ]
        },
        {
          "entity": "email-recheck-task",
          "effect": "reads",
          "facts": [
            "Task identity",
            "Name",
            "Lifecycle",
            "Email progress"
          ]
        }
      ],
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
    }
  ]
}
---

# Bounded status

## Trigger

Request the work inventory or status of the selected capture work.

## Outcome

Chat returns bounded status for the addressed existing task.
