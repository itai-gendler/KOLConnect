---
{
  "kind": "primary",
  "routes": {
    "offered": "Agency Detail"
  },
  "steps": [
    {
      "text": "Supply the selected organization's supported profile edits.",
      "kind": "actor",
      "actor": "local-user",
      "entities": [],
      "contexts": {
        "offered": {
          "place": "kolconnect-desktop::agency-detail"
        }
      }
    },
    {
      "text": "Supported selected agency facts are saved from detail.",
      "kind": "product",
      "actor": "local-user",
      "entities": [
        {
          "entity": "agency",
          "effect": "changes",
          "facts": [
            "Name",
            "Country",
            "Website",
            "Contact details",
            "Cooperation stage",
            "Descriptive owner",
            "Tags",
            "Notes",
            "Resources",
            "Follow-up times"
          ]
        }
      ],
      "contexts": {
        "offered": {
          "place": "kolconnect-desktop::agency-detail"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "webapp/pages/agencies.js"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/services/agency_service.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/storage/sqlite_agency_repository.py"
    }
  ]
}
---

# Save

## Trigger

Supply the selected organization's supported profile edits.

## Outcome

Supported selected agency facts are saved from detail.
