---
{
  "kind": "primary",
  "routes": {
    "offered": "Capture Tasks"
  },
  "steps": [
    {
      "text": "Request stopping the selected capture work.",
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
      "text": "Only when the selected family is Capture Task, apply this branch: A live worker receives a persisted stop request, moves through Stopping and reports Stopped after shutdown.",
      "kind": "product",
      "actor": "local-user",
      "entities": [
        {
          "entity": "capture-task",
          "effect": "changes",
          "facts": [
            "Control requests",
            "Lifecycle"
          ],
          "from": "Running",
          "to": "Stopping"
        },
        {
          "entity": "manual-task",
          "effect": "reads",
          "facts": [
            "Task identity",
            "Name",
            "Original inputs",
            "Manual account facts",
            "Confirmed fields",
            "Source/contact linkage",
            "Supplementation scope",
            "Lifecycle",
            "Control requests",
            "Progress",
            "Run summary",
            "Artifacts",
            "Import linkage"
          ]
        },
        {
          "entity": "email-recheck-task",
          "effect": "reads",
          "facts": [
            "Task identity",
            "Name",
            "Original inputs",
            "Candidate source",
            "Source-task/library scope",
            "Candidate Accounts",
            "Email scope",
            "Platform selection",
            "Lifecycle",
            "Control requests",
            "Email progress",
            "Run summary",
            "Artifacts",
            "Import outcome"
          ]
        }
      ],
      "contexts": {
        "offered": {
          "place": "kolconnect-desktop::capture-tasks"
        }
      }
    },
    {
      "text": "Only when the selected family is Manual Task, apply this branch: A live worker receives a persisted stop request, moves through Stopping and reports Stopped after shutdown.",
      "kind": "product",
      "actor": "local-user",
      "entities": [
        {
          "entity": "manual-task",
          "effect": "changes",
          "facts": [
            "Control requests",
            "Lifecycle"
          ],
          "from": "Running",
          "to": "Stopping"
        }
      ],
      "contexts": {
        "offered": {
          "place": "kolconnect-desktop::capture-tasks"
        }
      }
    },
    {
      "text": "Only when the selected family is Email Recheck Task, apply this branch: A live worker receives a persisted stop request, moves through Stopping and reports Stopped after shutdown.",
      "kind": "product",
      "actor": "local-user",
      "entities": [
        {
          "entity": "email-recheck-task",
          "effect": "changes",
          "facts": [
            "Control requests",
            "Lifecycle"
          ],
          "from": "Running",
          "to": "Stopping"
        }
      ],
      "contexts": {
        "offered": {
          "place": "kolconnect-desktop::capture-tasks"
        }
      }
    },
    {
      "text": "If the selected family is Capture Task, worker shutdown leaves it Stopped.",
      "kind": "product",
      "actor": "local-user",
      "entities": [
        {
          "entity": "capture-task",
          "effect": "changes",
          "facts": [
            "Lifecycle",
            "Control requests"
          ],
          "from": "Stopping",
          "to": "Stopped"
        }
      ],
      "contexts": {
        "offered": {
          "place": "kolconnect-desktop::capture-tasks"
        }
      }
    },
    {
      "text": "If the selected family is Manual Task, worker shutdown leaves it Stopped.",
      "kind": "product",
      "actor": "local-user",
      "entities": [
        {
          "entity": "manual-task",
          "effect": "changes",
          "facts": [
            "Lifecycle",
            "Control requests"
          ],
          "from": "Stopping",
          "to": "Stopped"
        }
      ],
      "contexts": {
        "offered": {
          "place": "kolconnect-desktop::capture-tasks"
        }
      }
    },
    {
      "text": "If the selected family is Email Recheck Task, worker shutdown leaves it Stopped.",
      "kind": "product",
      "actor": "local-user",
      "entities": [
        {
          "entity": "email-recheck-task",
          "effect": "changes",
          "facts": [
            "Lifecycle",
            "Control requests"
          ],
          "from": "Stopping",
          "to": "Stopped"
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
    }
  ]
}
---

# Stop active worker

## Trigger

Request stopping the selected capture work.

## Outcome

A live worker receives a persisted stop request, moves through Stopping and reports Stopped after shutdown.

## Decision points

### Selected task family

Which addressed task family is selected? Only the matching family branch runs; the alternatives converge on the stated outcome.

- Ordinary capture → apply only the Capture Task branch.
- Manual capture → apply only the Manual Task branch.
- Email recheck → apply only the Email Recheck Task branch.
