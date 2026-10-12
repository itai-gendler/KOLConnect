---
{
  "kind": "validation",
  "routes": {
    "offered": "Agency Detail"
  },
  "steps": [
    {
      "text": "Request deletion of the selected unreferenced organization.",
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
      "text": "Existing canonical profile or contact references block agency deletion.",
      "kind": "product",
      "actor": "local-user",
      "entities": [
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
        },
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
          "entity": "creator",
          "effect": "reads",
          "facts": [
            "Identity",
            "Name",
            "Country",
            "Language",
            "Content category",
            "Biography",
            "Contact details",
            "Tags",
            "Notes",
            "Descriptive owner",
            "Agency association",
            "Contact association",
            "Business status",
            "Archive time",
            "Update time",
            "Linked review task"
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

# Creator/Contact references refused

## Trigger

Request deletion of the selected unreferenced organization.

## Outcome

Existing canonical profile or contact references block agency deletion.
