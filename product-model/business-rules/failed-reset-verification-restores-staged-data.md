---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "reset-business-data",
      "contexts": [
        {
          "place": "kolconnect-desktop::clean-reset"
        }
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "webapp/pages/settings.js"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/http_handlers/clean_reset_handler.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/services/clean_reset_service.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/storage/sqlite_workbook_store.py"
    }
  ]
}
---

# Failed reset verification restores staged data

Reset verifies empty declared business rows and unchanged settings after backup/staging. Failure restores authoritative transaction backup, designated JSON and task artifacts; failed restoration/cleanup cannot be reported as success.
