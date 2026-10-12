---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "delete-agency",
      "contexts": [
        {
          "place": "kolconnect-desktop::agencies"
        },
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

# Referenced Agencies cannot be deleted

Existing canonical Creator or Agency Contact references prevent Agency deletion. The check is association integrity, not a caller grant.
