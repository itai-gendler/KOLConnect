---
{
  "kind": "primary",
  "routes": {
    "offered": "Campaigns"
  },
  "steps": [
    {
      "text": "Supply supported activity profile and business-status edits.",
      "kind": "actor",
      "actor": "local-user",
      "entities": [],
      "contexts": {
        "offered": {
          "place": "kolconnect-desktop::campaigns"
        }
      }
    },
    {
      "text": "The active campaign's supported profile/business-status values are saved.",
      "kind": "product",
      "actor": "local-user",
      "entities": [
        {
          "entity": "campaign",
          "effect": "changes",
          "facts": [
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
            "Business status"
          ]
        },
        {
          "entity": "product",
          "effect": "reads",
          "facts": [
            "Identity",
            "Name",
            "Company",
            "Notes",
            "Creation time",
            "Update time",
            "Archive time"
          ]
        }
      ],
      "contexts": {
        "offered": {
          "place": "kolconnect-desktop::campaigns"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "webapp/pages/campaigns.js"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/campaign_repository.py"
    }
  ]
}
---

# Supported active-campaign save

## Trigger

Supply supported activity profile and business-status edits.

## Outcome

The active campaign's supported profile/business-status values are saved.
