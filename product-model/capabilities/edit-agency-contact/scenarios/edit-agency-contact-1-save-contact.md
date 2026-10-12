---
{
  "kind": "primary",
  "routes": {
    "offered": "Agency Detail"
  },
  "steps": [
    {
      "text": "Supply supported contact edits and a valid organization association.",
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
      "text": "Supported contact facts and a valid agency association are saved.",
      "kind": "product",
      "actor": "local-user",
      "entities": [
        {
          "entity": "agency-contact",
          "effect": "changes",
          "facts": [
            "Agency association",
            "Name",
            "Position",
            "Addresses",
            "Language",
            "Status",
            "Descriptive owner",
            "Notes",
            "Follow-up times"
          ]
        },
        {
          "entity": "agency",
          "effect": "reads",
          "facts": [
            "Identity",
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

# Save Contact

## Trigger

Supply supported contact edits and a valid organization association.

## Outcome

Supported contact facts and a valid agency association are saved.
