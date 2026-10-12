---
{
  "kind": "primary",
  "routes": {
    "offered": "Creator Library"
  },
  "steps": [
    {
      "text": "Request setting the selected profile's archive marker.",
      "kind": "actor",
      "actor": "local-user",
      "entities": [],
      "contexts": {
        "offered": {
          "place": "kolconnect-desktop::creator-library"
        }
      }
    },
    {
      "text": "Archiving from the inventory sets the profile archive marker and retains identity, accounts and history.",
      "kind": "product",
      "actor": "local-user",
      "entities": [
        {
          "entity": "creator",
          "effect": "changes",
          "facts": [
            "Archive time",
            "Update time"
          ],
          "from": "Active",
          "to": "Archived"
        }
      ],
      "contexts": {
        "offered": {
          "place": "kolconnect-desktop::creator-library"
        }
      }
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

# Archive retains history

## Trigger

Request setting the selected profile's archive marker.

## Outcome

Archiving from the inventory sets the profile archive marker and retains identity, accounts and history.
