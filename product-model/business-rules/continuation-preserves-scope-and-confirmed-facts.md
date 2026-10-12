---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "start-task",
      "contexts": [
        {
          "place": "kolconnect-desktop::capture-tasks"
        }
      ]
    },
    {
      "type": "capability",
      "id": "resume-task",
      "contexts": [
        {
          "place": "kolconnect-desktop::capture-tasks"
        }
      ]
    },
    {
      "type": "capability",
      "id": "retry-failed-results",
      "contexts": [
        {
          "place": "kolconnect-desktop::capture-tasks"
        },
        {
          "place": "kolconnect-desktop::review-results"
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
      "target": "app/services/task_result_mapper.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/creator_repository.py"
    }
  ]
}
---

# Continuation preserves scope and confirmed facts

Continuation retains selected platform/input scope, skips successfully completed inputs and protects manual confirmed facts. Retry targets eligible failed inputs rather than rerunning every successful capture.
