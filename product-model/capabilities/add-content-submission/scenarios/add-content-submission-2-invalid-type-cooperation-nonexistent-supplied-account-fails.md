---
{
  "kind": "validation",
  "routes": {
    "offered": "Campaign Detail"
  },
  "steps": [
    {
      "text": "Supply a supported content type/reference and optional existing account association.",
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
      "text": "Invalid content type or nonexistent participation/supplied account prevents recording; existence validation does not establish same-profile account policy.",
      "kind": "product",
      "actor": "local-user",
      "entities": [
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
    }
  ]
}
---

# Invalid type/cooperation/nonexistent supplied Account fails

## Trigger

Supply a supported content type/reference and optional existing account association.

## Outcome

Invalid content type or nonexistent participation/supplied account prevents recording; existence validation does not establish same-profile account policy.
