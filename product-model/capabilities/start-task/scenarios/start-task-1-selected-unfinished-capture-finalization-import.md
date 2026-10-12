---
{
  "kind": "primary",
  "routes": {
    "offered": "Capture Tasks"
  },
  "steps": [
    {
      "text": "Select unfinished platform work or manual supplementation and request execution.",
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
      "text": "Selected unfinished ordinary capture starts, records per-input outcomes, finalizes controlled artifacts and imports eligible canonical facts before reporting Completed.",
      "kind": "product",
      "actor": "local-user",
      "entities": [
        {
          "entity": "capture-task",
          "effect": "changes",
          "facts": [
            "Lifecycle",
            "Control requests",
            "Progress",
            "Run summary"
          ],
          "from": "Created",
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
      "text": "Capture eligible unfinished inputs and retain per-account capture facts, statuses and errors; human review initially remains Pending.",
      "kind": "product",
      "actor": "local-user",
      "entities": [
        {
          "entity": "task-result",
          "effect": "creates",
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
          ],
          "to": "Pending"
        }
      ],
      "contexts": {
        "offered": {
          "place": "kolconnect-desktop::capture-tasks"
        }
      }
    },
    {
      "text": "Finish the selected capture scope and enter protected finalization.",
      "kind": "product",
      "actor": "local-user",
      "entities": [
        {
          "entity": "capture-task",
          "effect": "changes",
          "facts": [
            "Lifecycle",
            "Run summary",
            "Artifacts"
          ],
          "from": "Running",
          "to": "Finalizing"
        }
      ],
      "contexts": {
        "offered": {
          "place": "kolconnect-desktop::capture-tasks"
        }
      }
    },
    {
      "text": "If the eligible canonical identity is new, create its profile/account and supported capture/content history after the source result save. Human review remains independent.",
      "kind": "product",
      "actor": "local-user",
      "entities": [
        {
          "entity": "creator",
          "effect": "creates",
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
            "Linked review task",
            "Creation time"
          ],
          "to": "Active"
        },
        {
          "entity": "creator-account",
          "effect": "creates",
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
          ],
          "with": "creator"
        },
        {
          "entity": "creator-snapshot",
          "effect": "creates",
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
          ],
          "with": "creator"
        },
        {
          "entity": "current-video",
          "effect": "creates",
          "facts": [
            "Content identity",
            "Creator association",
            "Content URL",
            "Available views",
            "Available likes",
            "Available comments",
            "Capture time"
          ],
          "with": "creator"
        },
        {
          "entity": "video-snapshot",
          "effect": "creates",
          "facts": [
            "Observation identity",
            "Snapshot association",
            "Content identity",
            "Content URL",
            "Platform",
            "Available metrics",
            "Capture time",
            "Creator association"
          ],
          "with": "creator-snapshot"
        },
        {
          "entity": "task-result",
          "effect": "changes",
          "facts": [
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
      "text": "If the canonical identity already exists, update only supported imported facts under confirmed-field protection and create new source capture/content observations where their identities are new.",
      "kind": "product",
      "actor": "local-user",
      "entities": [
        {
          "entity": "creator",
          "effect": "changes",
          "facts": [
            "Name",
            "Country",
            "Language",
            "Content category",
            "Biography",
            "Contact details",
            "Notes",
            "Update time"
          ]
        },
        {
          "entity": "creator-account",
          "effect": "changes",
          "facts": [
            "Username",
            "Profile identity",
            "Account email",
            "Followers",
            "Latest post",
            "Capture status",
            "Capture time",
            "Source"
          ]
        },
        {
          "entity": "creator-snapshot",
          "effect": "creates",
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
          "effect": "creates",
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
          "effect": "creates",
          "facts": [
            "Observation identity",
            "Snapshot association",
            "Content identity",
            "Content URL",
            "Platform",
            "Available metrics",
            "Capture time",
            "Creator association"
          ],
          "with": "creator-snapshot"
        },
        {
          "entity": "task-result",
          "effect": "changes",
          "facts": [
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
      "text": "If the source capture/content identity is already retained, upsert its available observations while keeping the same identity.",
      "kind": "product",
      "actor": "local-user",
      "entities": [
        {
          "entity": "creator-snapshot",
          "effect": "changes",
          "facts": [
            "Source task",
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
          "effect": "changes",
          "facts": [
            "Content URL",
            "Available views",
            "Available likes",
            "Available comments",
            "Capture time"
          ]
        },
        {
          "entity": "video-snapshot",
          "effect": "changes",
          "facts": [
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
      "text": "Finalization and eligible canonical import complete with the selected work's type-specific outcome.",
      "kind": "product",
      "actor": "local-user",
      "entities": [
        {
          "entity": "capture-task",
          "effect": "changes",
          "facts": [
            "Lifecycle",
            "Progress",
            "Run summary",
            "Library import outcome"
          ],
          "from": "Finalizing",
          "to": "Completed"
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

# Selected unfinished capture/finalization/import

## Trigger

Select unfinished platform work or manual supplementation and request execution.

## Outcome

Selected unfinished ordinary capture starts, records per-input outcomes, finalizes controlled artifacts and imports eligible canonical facts before reporting Completed.


## Decision points

### Canonical and capture identity

Is the eligible canonical/source identity new or already retained? Only the matching import branch runs; each branch converges on canonical import completion.

- New canonical identity → create the profile and its supported dependent captures.
- Existing canonical identity with new capture identity → preserve canonical identity and apply supported import/create observations.
- Existing source capture identity → retain its identity and upsert supported source observations.
