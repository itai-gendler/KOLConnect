---
{
  "kind": "primary",
  "routes": {
    "offered": "Review Results"
  },
  "steps": [
    {
      "text": "Select failed inputs or all eligible failures for retry.",
      "kind": "actor",
      "actor": "local-user",
      "entities": [],
      "contexts": {
        "offered": {
          "place": "kolconnect-desktop::review-results"
        }
      }
    },
    {
      "text": "If Capture Task is the selected family, prepare only its eligible failed scope and reset this Completed work to Created.",
      "kind": "product",
      "actor": "local-user",
      "entities": [
        {
          "entity": "capture-task",
          "effect": "changes",
          "facts": [
            "Lifecycle",
            "Retry scope"
          ],
          "from": "Completed",
          "to": "Created"
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
          "place": "kolconnect-desktop::review-results"
        }
      }
    },
    {
      "text": "If Capture Task is the selected family, start the prepared selected platforms with one worker.",
      "kind": "product",
      "actor": "local-user",
      "entities": [
        {
          "entity": "capture-task",
          "effect": "changes",
          "facts": [
            "Lifecycle",
            "Control requests",
            "Progress"
          ],
          "from": "Created",
          "to": "Running"
        }
      ],
      "contexts": {
        "offered": {
          "place": "kolconnect-desktop::review-results"
        }
      }
    },
    {
      "text": "If Manual Task is the selected family, prepare only its eligible failed scope and reset this Completed work to Created.",
      "kind": "product",
      "actor": "local-user",
      "entities": [
        {
          "entity": "manual-task",
          "effect": "changes",
          "facts": [
            "Lifecycle",
            "Retry scope"
          ],
          "from": "Completed",
          "to": "Created"
        }
      ],
      "contexts": {
        "offered": {
          "place": "kolconnect-desktop::review-results"
        }
      }
    },
    {
      "text": "If Manual Task is the selected family, start the prepared selected platforms with one worker.",
      "kind": "product",
      "actor": "local-user",
      "entities": [
        {
          "entity": "manual-task",
          "effect": "changes",
          "facts": [
            "Lifecycle",
            "Control requests",
            "Progress"
          ],
          "from": "Created",
          "to": "Running"
        }
      ],
      "contexts": {
        "offered": {
          "place": "kolconnect-desktop::review-results"
        }
      }
    },
    {
      "text": "If Email Recheck Task is the selected family, prepare only its eligible failed scope and reset this Completed work to Created.",
      "kind": "product",
      "actor": "local-user",
      "entities": [
        {
          "entity": "email-recheck-task",
          "effect": "changes",
          "facts": [
            "Lifecycle",
            "Retry scope"
          ],
          "from": "Completed",
          "to": "Created"
        }
      ],
      "contexts": {
        "offered": {
          "place": "kolconnect-desktop::review-results"
        }
      }
    },
    {
      "text": "If Email Recheck Task is the selected family, start the prepared selected platforms with one worker.",
      "kind": "product",
      "actor": "local-user",
      "entities": [
        {
          "entity": "email-recheck-task",
          "effect": "changes",
          "facts": [
            "Lifecycle",
            "Control requests",
            "Email progress"
          ],
          "from": "Created",
          "to": "Running"
        }
      ],
      "contexts": {
        "offered": {
          "place": "kolconnect-desktop::review-results"
        }
      }
    },
    {
      "text": "The selected eligible failed results record supported per-account capture facts/status/errors during the restarted scope, independently of human review.",
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
          "place": "kolconnect-desktop::review-results"
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

# Retry selected/all failed inputs

## Trigger

Select failed inputs or all eligible failures for retry.

## Outcome

The results view retries the selected eligible failed inputs or all eligible failures.

## Decision points

### Selected task family

Which addressed task family is selected? Only the matching family branch runs; the alternatives converge on the stated outcome.

- Ordinary capture → apply only the Capture Task branch.
- Manual capture → apply only the Manual Task branch.
- Email recheck → apply only the Email Recheck Task branch.


## Edge cases

- Eligible failed scope can be prepared from other supported inactive states; the Completed case does not prevent retry from other eligible inactive states.
