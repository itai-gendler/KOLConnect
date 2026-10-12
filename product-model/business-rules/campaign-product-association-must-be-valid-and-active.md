---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "create-campaign",
      "contexts": [
        {
          "place": "kolconnect-desktop::campaigns"
        }
      ]
    },
    {
      "type": "capability",
      "id": "edit-campaign",
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

# Campaign Product association must be valid and active

Campaign creation and inspected ordinary profile saves require an existing Active Product association.
