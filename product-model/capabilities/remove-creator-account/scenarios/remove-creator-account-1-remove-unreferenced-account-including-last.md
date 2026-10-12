---
{
  "kind": "primary",
  "routes": {
    "offered": "Creator Detail"
  },
  "steps": [
    {
      "text": "Request removing the selected platform identity.",
      "kind": "actor",
      "actor": "local-user",
      "entities": [],
      "contexts": {
        "offered": {
          "place": "kolconnect-desktop::creator-detail"
        }
      }
    },
    {
      "text": "An unreferenced account is removed; this also succeeds when it is the profile's final account.",
      "kind": "product",
      "actor": "local-user",
      "entities": [
        {
          "entity": "creator-account",
          "effect": "removes"
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
        },
        {
          "entity": "actual-publication",
          "effect": "reads",
          "facts": [
            "Publication identity",
            "Cooperation association",
            "Platform",
            "Normalized content URL",
            "Actual Account",
            "Actual publication time",
            "Recording time",
            "Observation time",
            "Provenance"
          ]
        }
      ],
      "contexts": {
        "offered": {
          "place": "kolconnect-desktop::creator-detail"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "webapp/pages/creator-library-detail.js"
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
    }
  ]
}
---

# Remove unreferenced Account, including last

## Trigger

Request removing the selected platform identity.

## Outcome

An unreferenced account is removed; this also succeeds when it is the profile's final account.
