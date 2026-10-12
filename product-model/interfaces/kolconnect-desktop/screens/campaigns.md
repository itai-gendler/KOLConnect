---
{
  "entities": [
    {
      "entity": "campaign",
      "shows": [
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
      ],
      "collects": [
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
      "shows": [
        "Identity",
        "Name",
        "Archive time"
      ]
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

# Campaigns

Campaign inventory, Product association, status, archive state, budget and dates

 creation/edit facts.
