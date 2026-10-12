---
{
  "entities": [
    {
      "entity": "google-sheets-settings",
      "shows": [
        "Client configuration",
        "Target configuration",
        "Local OAuth authorization",
        "Connection status"
      ],
      "collects": [
        "Client configuration",
        "Target configuration"
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

# Google Sheets Integration

Client/target configuration, local authorization, connection and sync results.
