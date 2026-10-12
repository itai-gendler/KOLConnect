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

# Reset clears its declared compatibility scope

Reset clears the fourteen workbook-compatible business sheets, controlled task artifacts and designated data-protection/cached-mail JSON stores. Metadata and application/browser/mail/Feishu settings are preserved. Dependent SQLite brief/submission/publication effects follow supported parent removals; schema-6 mail facts/preferences and performance observations have no comprehensive wipe guarantee.
