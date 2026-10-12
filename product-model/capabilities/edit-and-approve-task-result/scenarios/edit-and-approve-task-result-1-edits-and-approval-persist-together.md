---
{
  "kind": "primary",
  "routes": {
    "offered": "Review Results"
  },
  "steps": [
    {
      "text": "Supply nonempty supported edits and request their combined approval.",
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
      "text": "Supported nonempty edits and approval persist together, then eligible library mutation completes.",
      "kind": "product",
      "actor": "local-user",
      "entities": [
        {
          "entity": "task-result",
          "effect": "changes",
          "facts": [
            "Confirmed edits",
            "Review decision",
            "Review time"
          ],
          "from": "Pending",
          "to": "Approved"
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
          "place": "kolconnect-desktop::review-results"
        }
      }
    },
    {
      "text": "When eligible completed/manual work has no recorded successful task import, if the eligible canonical identity is new, create its profile/account and supported capture/content history after the source result save. Human review remains independent.",
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
          "place": "kolconnect-desktop::review-results"
        }
      }
    },
    {
      "text": "When eligible completed/manual work has no recorded successful task import, if the canonical identity already exists, update only supported imported facts under confirmed-field protection and create new source capture/content observations where their identities are new.",
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
          "place": "kolconnect-desktop::review-results"
        }
      }
    },
    {
      "text": "When eligible completed/manual work has no recorded successful task import, if the source capture/content identity is already retained, upsert its available observations while keeping the same identity.",
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
          "place": "kolconnect-desktop::review-results"
        }
      }
    },
    {
      "text": "When Capture Task is the addressed family and its eligible import returns a successful import time, record its task-level outcome and canonical import linkage. An already-imported or skipped result does not rewrite this marker.",
      "kind": "product",
      "actor": "local-user",
      "contexts": {
        "offered": {
          "place": "kolconnect-desktop::review-results"
        }
      },
      "entities": [
        {
          "entity": "capture-task",
          "effect": "changes",
          "facts": [
            "Library import outcome"
          ]
        }
      ]
    },
    {
      "text": "When Manual Task is the addressed family and its eligible import returns a successful import time, record its task-level outcome and canonical import linkage. An already-imported or skipped result does not rewrite this marker.",
      "kind": "product",
      "actor": "local-user",
      "contexts": {
        "offered": {
          "place": "kolconnect-desktop::review-results"
        }
      },
      "entities": [
        {
          "entity": "manual-task",
          "effect": "changes",
          "facts": [
            "Import linkage"
          ]
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
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/services/task_service.py#_complete_review_creator_mutation"
    }
  ]
}
---

# Edits and approval persist together

## Trigger

Supply nonempty supported edits and request their combined approval.

## Outcome

Supported nonempty edits and approval persist together, then eligible library mutation completes.


## Decision points

### Canonical and capture identity

Is the eligible canonical/source identity new or already retained? Only the matching import branch runs; each branch converges on canonical import completion.

- New canonical identity → create the profile and its supported dependent captures.
- Existing canonical identity with new capture identity → preserve canonical identity and apply supported import/create observations.
- Existing source capture identity → retain its identity and upsert supported source observations.

## Edge cases

- When this task already has a successful recorded library import, review/edits still persist but approval reports already imported and does not reimport canonical records. Eligible unfinished work retains the review/edits without importing.
