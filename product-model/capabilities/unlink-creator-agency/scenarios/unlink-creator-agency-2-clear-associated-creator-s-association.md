---
{
  "kind": "primary",
  "routes": {
    "offered": "Agency Detail"
  },
  "steps": [
    {
      "text": "Request clearing the selected profile's organization/contact association.",
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
      "text": "Agency detail clears the selected related profile's agency/contact association without deleting the agency.",
      "kind": "product",
      "actor": "local-user",
      "entities": [
        {
          "entity": "creator",
          "effect": "changes",
          "facts": [
            "Agency association",
            "Contact association",
            "Update time"
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
      "target": "webapp/pages/creator-library-detail.js"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/services/creator_service.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/storage/sqlite_creator_repository.py"
    },
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

# Clear associated Creator’s association

## Trigger

Request clearing the selected profile's organization/contact association.

## Outcome

Agency detail clears the selected related profile's agency/contact association without deleting the agency.
