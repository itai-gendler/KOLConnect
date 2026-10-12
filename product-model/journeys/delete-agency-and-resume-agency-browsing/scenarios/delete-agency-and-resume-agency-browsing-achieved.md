---
{
  "kind": "primary",
  "result": "achieved",
  "routes": {
    "detail": "Agency Detail"
  },
  "steps": [
    {
      "text": "Request deletion of the selected unreferenced organization.",
      "kind": "actor",
      "actor": "local-user",
      "capability": "delete-agency",
      "entities": [],
      "contexts": {
        "detail": {
          "place": "kolconnect-desktop::agency-detail"
        }
      }
    },
    {
      "text": "Delete the unreferenced Agency and carry the user to agency inventory.",
      "kind": "product",
      "actor": "local-user",
      "capability": "delete-agency",
      "entities": [
        {
          "entity": "agency",
          "effect": "removes"
        }
      ],
      "contexts": {
        "detail": {
          "place": "kolconnect-desktop::agencies"
        }
      }
    },
    {
      "text": "Request the inventory returned after deletion.",
      "kind": "actor",
      "actor": "local-user",
      "capability": "browse-agencies",
      "entities": [],
      "contexts": {
        "detail": {
          "place": "kolconnect-desktop::agencies"
        }
      }
    },
    {
      "text": "Unreferenced deletion succeeds and the returned inventory excludes the deleted agency identity.",
      "kind": "product",
      "actor": "local-user",
      "capability": "browse-agencies",
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
        "detail": {
          "place": "kolconnect-desktop::agencies"
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

# Deleted Agency absent from inventory

## Trigger

Request deletion of the selected unreferenced organization.

## Outcome

Unreferenced deletion succeeds and the returned inventory excludes the deleted agency identity.
