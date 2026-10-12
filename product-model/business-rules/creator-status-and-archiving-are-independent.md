---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "change-creator-status",
      "contexts": [
        {
          "place": "kolconnect-desktop::creator-library"
        }
      ]
    },
    {
      "type": "capability",
      "id": "archive-creator",
      "contexts": [
        {
          "place": "kolconnect-desktop::creator-library"
        },
        {
          "place": "kolconnect-desktop::creator-detail"
        }
      ]
    },
    {
      "type": "capability",
      "id": "restore-creator",
      "contexts": [
        {
          "place": "kolconnect-desktop::creator-library"
        },
        {
          "place": "kolconnect-desktop::creator-detail"
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
      "target": "webapp/pages/creator-library-detail.js"
    }
  ]
}
---

# Creator status and archiving are independent

Business status and archiving are independent. Archive retains canonical identity/history; restore clears the archive marker without replacing the recorded status.
