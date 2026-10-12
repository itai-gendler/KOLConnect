---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "edit-campaign",
      "contexts": [
        {
          "place": "kolconnect-desktop::campaigns"
        }
      ]
    },
    {
      "type": "capability",
      "id": "archive-campaign",
      "contexts": [
        {
          "place": "kolconnect-desktop::campaigns"
        }
      ]
    },
    {
      "type": "capability",
      "id": "restore-campaign",
      "contexts": [
        {
          "place": "kolconnect-desktop::campaigns"
        }
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

# Campaign business status and archiving are independent

Campaign business status and archive marker are independent. Desktop inventory disables archived editing; ordinary cooperation, optimized scalar updates and direct execution enforce their own path-specific checks.
