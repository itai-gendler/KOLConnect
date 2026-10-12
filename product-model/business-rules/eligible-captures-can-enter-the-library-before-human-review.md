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
      "id": "approve-task-result",
      "contexts": [
        {
          "place": "kolconnect-desktop::review-results"
        }
      ]
    },
    {
      "type": "capability",
      "id": "edit-and-approve-task-result",
      "contexts": [
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

# Eligible captures can enter the library before human review

Eligible captures can enter the canonical library during finalization before human review. Completed/manual approval performs eligible canonical mutation; unfinished approval can retain Approved without importing.
