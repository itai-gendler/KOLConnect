---
{
  "kind": "validation",
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
      "text": "Invalid facts or association are refused without save.",
      "kind": "product",
      "actor": "local-user",
      "entities": [
        {
          "entity": "agency-contact",
          "effect": "reads",
          "facts": [
            "Identity",
            "Agency association",
            "Name",
            "Position",
            "Addresses",
            "Language",
            "Status",
            "Descriptive owner",
            "Notes",
            "Follow-up times",
            "Source"
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

# Invalid facts/reference refused

## Trigger

Supply supported contact edits and a valid organization association.

## Outcome

Invalid facts or association are refused without save.
