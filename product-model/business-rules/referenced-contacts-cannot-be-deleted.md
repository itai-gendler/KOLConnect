---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "delete-agency-contact",
      "contexts": [
        {
          "place": "kolconnect-desktop::agency-detail"
        }
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

# Referenced Contacts cannot be deleted

A Creator's selected contact association prevents direct contact deletion. No retained reference-count fact is required.
