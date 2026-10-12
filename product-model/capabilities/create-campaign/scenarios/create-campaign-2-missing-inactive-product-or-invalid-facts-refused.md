---
{
  "kind": "validation",
  "routes": {
    "offered": "Campaigns"
  },
  "steps": [
    {
      "text": "Supply activity facts and a valid active promoted-offering association.",
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
      "text": "Missing/inactive product association or invalid required campaign facts prevent creation.",
      "kind": "product",
      "actor": "local-user",
      "entities": [
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

# Missing/inactive Product or invalid facts refused

## Trigger

Supply activity facts and a valid active promoted-offering association.

## Outcome

Missing/inactive product association or invalid required campaign facts prevent creation.
