---
{
  "kind": "primary",
  "routes": {
    "offered": "Capture Tasks"
  },
  "steps": [
    {
      "text": "Request continuing paused or interrupted capture work.",
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
      "text": "Only when the selected family is Capture Task, apply this branch: Interrupted or otherwise eligible workerless resumable work is restarted within scope, skipping successful inputs.",
      "kind": "product",
      "actor": "local-user",
      "entities": [
        {
          "entity": "capture-task",
          "effect": "changes",
          "facts": [
            "Control requests",
            "Lifecycle",
            "Progress"
          ],
          "from": "Interrupted",
          "to": "Running"
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
        },
        {
          "entity": "task-result",
          "effect": "reads",
          "facts": [
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
      "text": "Only when the selected family is Manual Task, apply this branch: Interrupted or otherwise eligible workerless resumable work is restarted within scope, skipping successful inputs.",
      "kind": "product",
      "actor": "local-user",
      "entities": [
        {
          "entity": "manual-task",
          "effect": "changes",
          "facts": [
            "Control requests",
            "Lifecycle",
            "Progress"
          ],
          "from": "Interrupted",
          "to": "Running"
        }
      ],
      "contexts": {
        "offered": {
          "place": "kolconnect-desktop::capture-tasks"
        }
      }
    },
    {
      "text": "Only when the selected family is Email Recheck Task, apply this branch: Interrupted or otherwise eligible workerless resumable work is restarted within scope, skipping successful inputs.",
      "kind": "product",
      "actor": "local-user",
      "entities": [
        {
          "entity": "email-recheck-task",
          "effect": "changes",
          "facts": [
            "Control requests",
            "Lifecycle",
            "Email progress"
          ],
          "from": "Interrupted",
          "to": "Running"
        }
      ],
      "contexts": {
        "offered": {
          "place": "kolconnect-desktop::capture-tasks"
        }
      }
    },
    {
      "text": "Eligible unfinished capture progress updates existing per-account capture facts, status and errors while preserving confirmed fields and human review.",
      "kind": "product",
      "actor": "local-user",
      "entities": [
        {
          "entity": "task-result",
          "effect": "changes",
          "facts": [
            "Capture facts",
            "Capture status",
            "Capture error"
          ]
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

# Restart interrupted/workerless resumable task

## Trigger

Request continuing paused or interrupted capture work.

## Outcome

Interrupted or otherwise eligible workerless resumable work is restarted within scope, skipping successful inputs.

## Decision points

### Selected task family

Which addressed task family is selected? Only the matching family branch runs; the alternatives converge on the stated outcome.

- Ordinary capture → apply only the Capture Task branch.
- Manual capture → apply only the Manual Task branch.
- Email recheck → apply only the Email Recheck Task branch.
