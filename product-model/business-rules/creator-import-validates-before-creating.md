---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "import-creators",
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
      "target": "app/creator_batch_import.py"
    }
  ]
}
---

# Creator import validates before creating

The import batch is validated before canonical creation. Existing canonical account identities are skipped rather than imported again or silently reassigned.
