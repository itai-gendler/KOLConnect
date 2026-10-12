---
{
  "entities": [
    {
      "entity": "capture-task",
      "shows": [
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
      "collects": [
        "Name",
        "Original inputs",
        "Platform scope"
      ]
    },
    {
      "entity": "manual-task",
      "shows": [
        "Task identity",
        "Name",
        "Manual account facts",
        "Confirmed fields",
        "Source/contact linkage",
        "Supplementation scope",
        "Lifecycle",
        "Progress",
        "Run summary",
        "Artifacts",
        "Import linkage",
        "Original inputs",
        "Control requests",
        "Retry scope"
      ],
      "collects": [
        "Name",
        "Original inputs"
      ]
    },
    {
      "entity": "email-recheck-task",
      "shows": [
        "Task identity",
        "Name",
        "Candidate source",
        "Source-task/library scope",
        "Candidate Accounts",
        "Email scope",
        "Platform selection",
        "Lifecycle",
        "Email progress",
        "Run summary",
        "Artifacts",
        "Import outcome",
        "Original inputs",
        "Control requests",
        "Retry scope"
      ],
      "collects": [
        "Name",
        "Platform selection",
        "Original inputs"
      ]
    },
    {
      "entity": "task-result",
      "shows": [
        "Capture status",
        "Capture error",
        "Task/account identity"
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
    }
  ]
}
---

# Capture Tasks

Task identity, original inputs, platform scope, lifecycle, progress, retry/import outcomes and artifacts

 task names, links and execution scope.
