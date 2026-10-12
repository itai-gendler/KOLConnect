---
{
  "kind": "primary",
  "routes": {
    "offered": "Campaign Detail"
  },
  "steps": [
    {
      "text": "Supply supported cooperation terms, quote, cost, plans, results and execution edits.",
      "kind": "actor",
      "actor": "local-user",
      "entities": [],
      "contexts": {
        "offered": {
          "place": "kolconnect-desktop::campaign-detail"
        }
      }
    },
    {
      "text": "Validated ordinary stage, planned dates, structured quote, cost, recorded results and subsequent execution facts are saved. Changed execution-account selection and supplied actual-publication rows are part of the preceding validated relation save.",
      "kind": "product",
      "actor": "local-user",
      "entities": [
        {
          "entity": "campaign-creator",
          "effect": "changes",
          "facts": [
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
            "Execution Accounts"
          ]
        },
        {
          "entity": "actual-publication",
          "as": "new-publication",
          "effect": "creates",
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
        },
        {
          "entity": "actual-publication",
          "as": "retained-publication",
          "effect": "changes",
          "facts": [
            "Cooperation association",
            "Platform",
            "Normalized content URL",
            "Actual Account",
            "Actual publication time",
            "Recording time",
            "Observation time",
            "Provenance"
          ]
        },
        {
          "entity": "actual-publication",
          "as": "removed-publication",
          "effect": "removes"
        },
        {
          "entity": "campaign",
          "effect": "reads",
          "facts": [
            "Identity",
            "Name",
            "Product association",
            "Country",
            "Target platforms",
            "Start date",
            "End date",
            "Descriptive owner",
            "Budget",
            "Goal",
            "Notes",
            "Business status",
            "Archive time"
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
        }
      ],
      "contexts": {
        "offered": {
          "place": "kolconnect-desktop::campaign-detail"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "webapp/pages/campaign-detail.js"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/http_handlers/campaign_handler.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/services/campaign_creator_service.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/services/campaign_execution_service.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/domain/publication.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/domain/money.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/campaign_creator_repository.py"
    }
  ]
}
---

# Supported cooperation save

## Trigger

Supply supported cooperation terms, quote, cost, plans, results and execution edits.

## Outcome

Validated ordinary stage, planned dates, structured quote, cost, recorded results and subsequent execution facts are saved.


## Edge cases

- When actual-publication rows accompany this save, only the changed rows apply: new records are created, retained records updated and explicitly removed rows removed. Normalized identity, optional actual account/time and same-Creator affiliation validation still apply; planned facts are not substituted for actual facts.
