---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "export-creators",
      "contexts": [
        {
          "place": "kolconnect-desktop::creator-library"
        }
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "webapp/pages/creator-library.js"
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
      "target": "app/creator_library_export.py"
    }
  ]
}
---

# Creator export is selected and bounded

Export requires a nonempty known selection and discloses only selected supported canonical profile/account facts.
