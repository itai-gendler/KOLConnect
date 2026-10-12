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
      ],
      "collects": [
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
      "entity": "creator",
      "shows": [
        "Identity",
        "Name",
        "Agency association",
        "Contact association"
      ]
    },
    {
      "entity": "campaign",
      "shows": [
        "Identity",
        "Name",
        "Business status"
      ]
    },
    {
      "entity": "campaign-creator",
      "shows": [
        "Cooperation stage",
        "Creator association",
        "Campaign association"
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

# Agency Detail

Selected Agency, Contacts, associated Creators and campaigns

 Agency/Contact facts.
