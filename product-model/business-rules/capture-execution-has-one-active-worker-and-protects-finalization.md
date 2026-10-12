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

# Capture execution has one active worker and protects finalization

Only one capture worker runs at a time. Concurrent starts/continuations are refused, and Finalizing protects work from start, resume, pause, stop or retry controls that would interrupt finalization.
