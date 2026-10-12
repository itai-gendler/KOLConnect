---
{
  "entities": [
    {
      "entity": "capture-task",
      "shows": [
        "Task identity",
        "Name",
        "Lifecycle",
        "Library import outcome"
      ]
    },
    {
      "entity": "manual-task",
      "shows": [
        "Task identity",
        "Name",
        "Lifecycle",
        "Import linkage"
      ]
    },
    {
      "entity": "email-recheck-task",
      "shows": [
        "Task identity",
        "Name",
        "Lifecycle",
        "Import outcome"
      ]
    },
    {
      "entity": "task-result",
      "shows": [
        "Task/account identity",
        "Capture facts",
        "Capture status",
        "Capture error",
        "Confirmed edits",
        "Review decision",
        "Review reason",
        "Review time",
        "Creator import linkage",
        "Account import linkage"
      ],
      "collects": [
        "Confirmed edits",
        "Review decision",
        "Review reason"
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
      "target": "app/services/task_service.py"
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

# Review Results

Task Result capture facts, confirmed fields, review decision and library outcome

 edits, notes and decisions.
