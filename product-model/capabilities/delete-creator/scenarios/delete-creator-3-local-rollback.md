---
{
  "kind": "edge",
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
      "text": "A local staged failure reports failure and restores the original local records.",
      "kind": "product",
      "actor": "local-user",
      "entities": [
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
        },
        {
          "entity": "legacy-cooperation",
          "effect": "reads",
          "facts": [
            "Historical identity",
            "Creator association",
            "Campaign description",
            "Platform",
            "Contact date",
            "Untyped price",
            "Publication count",
            "Recorded views",
            "Recorded ROI",
            "Result",
            "Notes",
            "Creation time"
          ]
        },
        {
          "entity": "campaign-creator",
          "effect": "reads",
          "facts": [
            "Participation identity",
            "Campaign association",
            "Creator association",
            "Execution Accounts",
            "Cooperation stage",
            "Quote currency",
            "Quote unit amount",
            "Quote quantity",
            "Pricing unit",
            "Quote total",
            "Cost",
            "Cost currency",
            "Planned publication dates",
            "Compatibility publication facts",
            "Recorded metrics",
            "Recorded ROI",
            "Performance notes",
            "Responsibility",
            "Next action",
            "Due date",
            "Waiting on",
            "Decision needed",
            "Last progress time",
            "Archive time"
          ]
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

# Local rollback

## Trigger

Preview the selected profile's deletion and explicitly confirm the current safe plan.

## Outcome

A local staged failure reports failure and restores the original local records.
