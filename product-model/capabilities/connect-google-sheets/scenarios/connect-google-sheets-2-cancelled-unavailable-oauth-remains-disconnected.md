---
{
  "kind": "edge",
  "routes": {
    "offered": "Google Sheets Integration"
  },
  "steps": [
    {
      "text": "Start connection and complete the offered external Google authorization.",
      "kind": "actor",
      "actor": "local-user",
      "entities": [],
      "contexts": {
        "offered": {
          "place": "kolconnect-desktop::google-sheets-integration"
        }
      }
    },
    {
      "text": "Cancelled or unavailable authorization leaves the connection disconnected.",
      "kind": "product",
      "actor": "local-user",
      "entities": [
        {
          "entity": "google-sheets-settings",
          "effect": "reads",
          "facts": [
            "Client configuration",
            "Target configuration",
            "Local OAuth authorization",
            "Connection status"
          ]
        }
      ],
      "contexts": {
        "offered": {
          "place": "kolconnect-desktop::google-sheets-integration"
        }
      }
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

# Cancelled/unavailable OAuth remains disconnected

## Trigger

Start connection and complete the offered external Google authorization.

## Outcome

Cancelled or unavailable authorization leaves the connection disconnected.
