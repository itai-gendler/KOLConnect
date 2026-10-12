---
{
  "actors": [
    "local-user"
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

# Delete an Agency and resume Agency browsing

## Goal

Delete the selected unreferenced Agency and resume browsing agencies.

## Success criterion

The resulting Agency inventory excludes the deleted identity.
