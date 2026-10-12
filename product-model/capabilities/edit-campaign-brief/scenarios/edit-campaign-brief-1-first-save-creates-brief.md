---
{
  "kind": "primary",
  "routes": {
    "offered": "Campaign Detail"
  },
  "steps": [
    {
      "text": "Supply the brief title, requirements, references and platform guidance.",
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
      "text": "The first valid brief save creates the campaign's requirements and guidance.",
      "kind": "product",
      "actor": "local-user",
      "entities": [
        {
          "entity": "campaign-brief",
          "effect": "creates",
          "facts": [
            "Campaign association",
            "Title",
            "Selling points",
            "Required content",
            "Forbidden content",
            "Brand requirements",
            "Content requirements",
            "Publication requirements",
            "References",
            "Platform guidance"
          ]
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

# First save creates Brief

## Trigger

Supply the brief title, requirements, references and platform guidance.

## Outcome

The first valid brief save creates the campaign's requirements and guidance.
