---
{
  "singleton": true,
  "domain": "integrations",
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "webapp/pages/settings.js"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/http_handlers/google_sheets_handler.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/services/google_sheets_data_sync_service.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/google_sheets_client.py"
    }
  ]
}
---

# Google Sheets Settings

The product's one Google Sheets client, target and local authorization configuration.

## Information kept

- **Client configuration** — Configured Google OAuth client details.
- **Target configuration** — Configured spreadsheet and managed worksheet targets.
- **Local OAuth authorization** — Locally retained OAuth authorization, removed on disconnect.
- **Connection status** — Current local connection status.
