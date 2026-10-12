---
{
  "entities": [
    {
      "entity": "data-settings",
      "shows": [
        "Configured source location",
        "Current authority",
        "Current source information"
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

# Clean Reset

Declared clear/preserve scope, counts, backup and verification

 confirmation.
