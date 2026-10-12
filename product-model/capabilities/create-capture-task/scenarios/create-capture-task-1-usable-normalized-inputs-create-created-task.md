---
{
  "kind": "primary",
  "routes": {
    "offered": "Capture Tasks"
  },
  "steps": [
    {
      "text": "Supply usable profile links, name and platform scope; confirm the scoped conversational request when using Chat.",
      "kind": "actor",
      "actor": "local-user",
      "entities": [],
      "contexts": {
        "offered": {
          "place": "kolconnect-desktop::capture-tasks"
        }
      }
    },
    {
      "text": "Usable normalized links and selected platforms create ordinary work in Created without starting a worker.",
      "kind": "product",
      "actor": "local-user",
      "entities": [
        {
          "entity": "capture-task",
          "effect": "creates",
          "facts": [
            "Task identity",
            "Name",
            "Original inputs",
            "Normalization results",
            "Platform scope",
            "Lifecycle",
            "Control requests",
            "Progress",
            "Run summary",
            "Artifacts",
            "Retry scope",
            "Library import outcome"
          ],
          "to": "Created"
        }
      ],
      "contexts": {
        "offered": {
          "place": "kolconnect-desktop::capture-tasks"
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

# Usable normalized inputs create Created task

## Trigger

Supply usable profile links, name and platform scope; confirm the scoped conversational request when using Chat.

## Outcome

Usable normalized links and selected platforms create ordinary work in Created without starting a worker.
