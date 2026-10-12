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
      "id": "pause-task",
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
      "id": "stop-task",
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
    },
    {
      "type": "entity",
      "id": "runtime-log"
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

# Exposed task activity is recorded

Exposed capture execution and pause/resume/stop/retry activity is recorded with event time, scope and message in Runtime Log. The incidental recording belongs to this Rule, not extra mutation Steps.
