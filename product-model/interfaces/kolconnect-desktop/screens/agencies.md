---
{
  "entities": [
    {
      "entity": "agency",
      "shows": [
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
      ],
      "collects": [
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
      "shows": [
        "Agency association"
      ]
    },
    {
      "entity": "creator",
      "shows": [
        "Identity",
        "Agency association",
        "Contact association"
      ]
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

# Agencies

Agency inventory and reference summaries

 selected Agency editing.
