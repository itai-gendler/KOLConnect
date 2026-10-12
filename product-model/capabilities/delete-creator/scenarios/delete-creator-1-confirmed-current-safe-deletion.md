---
{
  "kind": "primary",
  "routes": {
    "offered": "Creator Library"
  },
  "steps": [
    {
      "text": "Preview the selected profile's deletion and explicitly confirm the current safe plan.",
      "kind": "actor",
      "actor": "local-user",
      "entities": [],
      "contexts": {
        "offered": {
          "place": "kolconnect-desktop::creator-library"
        }
      }
    },
    {
      "text": "A fresh blocker-free deletion plan with explicit confirmation commits local removal of the selected profile and plan-selected dependents.",
      "kind": "product",
      "actor": "local-user",
      "entities": [
        {
          "entity": "creator",
          "effect": "removes",
          "from": "Active"
        },
        {
          "entity": "creator-account",
          "effect": "removes",
          "with": "creator"
        },
        {
          "entity": "creator-snapshot",
          "effect": "removes",
          "with": "creator"
        },
        {
          "entity": "video-snapshot",
          "effect": "removes",
          "with": "creator-snapshot"
        },
        {
          "entity": "current-video",
          "effect": "removes",
          "with": "creator"
        },
        {
          "entity": "legacy-cooperation",
          "effect": "removes",
          "with": "creator"
        },
        {
          "entity": "campaign-creator",
          "effect": "removes",
          "with": "creator",
          "from": "Active"
        },
        {
          "entity": "content-submission",
          "effect": "removes",
          "with": "campaign-creator",
          "from": "Pending"
        },
        {
          "entity": "actual-publication",
          "effect": "removes",
          "with": "campaign-creator"
        }
      ],
      "contexts": {
        "offered": {
          "place": "kolconnect-desktop::creator-library"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "webapp/pages/creator-library.js"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/services/creator_service.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/storage/sqlite_creator_repository.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/services/creator_hard_delete_service.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/services/creator_delete_plan.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/repositories/creator_hard_delete_repository.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/staged_delete_transaction.py"
    }
  ]
}
---

# Confirmed current safe deletion

## Trigger

Preview the selected profile's deletion and explicitly confirm the current safe plan.

## Outcome

A fresh blocker-free deletion plan with explicit confirmation commits local removal of the selected profile and plan-selected dependents.


## Edge cases

- The selected records here are Active and submissions/results Pending. Other retained archive or review states do not by themselves change this safe confirmed removal's outcome; reference/plan blockers remain in force.
