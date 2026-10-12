---
{
  "availability": [
    {
      "place": "kolconnect-desktop"
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
      "target": "app/http_handlers/settings_handler.py"
    }
  ],
  "domain": "advanced"
}
---

# Check system health

Check configured workbook, declared sheets, local configuration and recent extension imports without remote connector requests; this does not establish comprehensive active-SQLite integrity.
