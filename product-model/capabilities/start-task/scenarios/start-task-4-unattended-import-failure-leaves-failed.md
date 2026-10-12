---
{
  "kind": "edge",
  "routes": {
    "offered": "Capture Tasks"
  },
  "steps": [
    {
      "text": "The addressed task is Finalizing when its unattended canonical-library import fails.",
      "kind": "condition",
      "entities": [
        {
          "entity": "capture-task",
          "effect": "reads",
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
          ]
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
        },
        {
          "entity": "creator",
          "effect": "reads",
          "facts": [
            "Identity",
            "Name",
            "Country",
            "Language",
            "Content category",
            "Biography",
            "Contact details",
            "Tags",
            "Notes",
            "Descriptive owner",
            "Agency association",
            "Contact association",
            "Business status",
            "Archive time",
            "Update time",
            "Linked review task"
          ]
        },
        {
          "entity": "creator-account",
          "effect": "reads",
          "facts": [
            "Canonical identity",
            "Platform",
            "Profile identity",
            "Username",
            "Creator association",
            "Account email",
            "Followers",
            "Latest post",
            "Capture status",
            "Capture time",
            "Source",
            "Notes"
          ]
        },
        {
          "entity": "creator-snapshot",
          "effect": "reads",
          "facts": [
            "Capture identity",
            "Source task",
            "Creator association",
            "Observed account",
            "Observed metrics",
            "Score",
            "Level",
            "Capture time",
            "Source"
          ]
        },
        {
          "entity": "current-video",
          "effect": "reads",
          "facts": [
            "Content identity",
            "Creator association",
            "Content URL",
            "Available views",
            "Available likes",
            "Available comments",
            "Capture time"
          ]
        },
        {
          "entity": "video-snapshot",
          "effect": "reads",
          "facts": [
            "Observation identity",
            "Snapshot association",
            "Content identity",
            "Content URL",
            "Platform",
            "Available metrics",
            "Capture time"
          ]
        }
      ],
      "contexts": {
        "offered": {
          "place": "kolconnect-desktop::capture-tasks"
        }
      },
      "unattended": true
    },
    {
      "text": "Only when the selected family is Capture Task, apply this branch: An unattended finalization/import failure leaves the work Failed with its failure outcome rather than claiming successful library import.",
      "kind": "product",
      "entities": [
        {
          "entity": "capture-task",
          "effect": "changes",
          "facts": [
            "Lifecycle",
            "Run summary"
          ],
          "from": "Finalizing",
          "to": "Failed"
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
        },
        {
          "entity": "creator",
          "effect": "reads",
          "facts": [
            "Identity",
            "Name",
            "Country",
            "Language",
            "Content category",
            "Biography",
            "Contact details",
            "Tags",
            "Notes",
            "Descriptive owner",
            "Agency association",
            "Contact association",
            "Business status",
            "Archive time",
            "Update time",
            "Linked review task"
          ]
        },
        {
          "entity": "creator-account",
          "effect": "reads",
          "facts": [
            "Canonical identity",
            "Platform",
            "Profile identity",
            "Username",
            "Creator association",
            "Account email",
            "Followers",
            "Latest post",
            "Capture status",
            "Capture time",
            "Source",
            "Notes"
          ]
        },
        {
          "entity": "creator-snapshot",
          "effect": "reads",
          "facts": [
            "Capture identity",
            "Source task",
            "Creator association",
            "Observed account",
            "Observed metrics",
            "Score",
            "Level",
            "Capture time",
            "Source"
          ]
        },
        {
          "entity": "current-video",
          "effect": "reads",
          "facts": [
            "Content identity",
            "Creator association",
            "Content URL",
            "Available views",
            "Available likes",
            "Available comments",
            "Capture time"
          ]
        },
        {
          "entity": "video-snapshot",
          "effect": "reads",
          "facts": [
            "Observation identity",
            "Snapshot association",
            "Content identity",
            "Content URL",
            "Platform",
            "Available metrics",
            "Capture time"
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
      "text": "Only when the selected family is Manual Task, apply this branch: An unattended finalization/import failure leaves the work Failed with its failure outcome rather than claiming successful library import.",
      "kind": "product",
      "entities": [
        {
          "entity": "manual-task",
          "effect": "changes",
          "facts": [
            "Lifecycle",
            "Run summary"
          ],
          "from": "Finalizing",
          "to": "Failed"
        }
      ],
      "contexts": {
        "offered": {
          "place": "kolconnect-desktop::capture-tasks"
        }
      }
    },
    {
      "text": "Only when the selected family is Email Recheck Task, apply this branch: An unattended finalization/import failure leaves the work Failed with its failure outcome rather than claiming successful library import.",
      "kind": "product",
      "entities": [
        {
          "entity": "email-recheck-task",
          "effect": "changes",
          "facts": [
            "Lifecycle",
            "Run summary"
          ],
          "from": "Finalizing",
          "to": "Failed"
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

# Unattended import failure leaves Failed

## Trigger

The unattended worker/finalization condition arises for addressed task work.

## Outcome

An unattended finalization/import failure leaves the work Failed with its failure outcome rather than claiming successful library import.

## Decision points

### Selected task family

Which addressed task family is selected? Only the matching family branch runs; the alternatives converge on the stated outcome.

- Ordinary capture → apply only the Capture Task branch.
- Manual capture → apply only the Manual Task branch.
- Email recheck → apply only the Email Recheck Task branch.
