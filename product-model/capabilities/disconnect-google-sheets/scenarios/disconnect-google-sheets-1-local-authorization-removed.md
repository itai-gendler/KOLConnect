---
{
  "kind": "primary",
  "routes": {
    "offered": "Google Sheets Integration"
  },
  "steps": [
    {
      "text": "Request disconnecting local Google authorization.",
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
      "text": "Local Google authorization is removed; remote worksheets are retained.",
      "kind": "product",
      "actor": "local-user",
      "entities": [
        {
          "entity": "google-sheets-settings",
          "effect": "changes",
          "facts": [
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

# Local authorization removed

## Trigger

Request disconnecting local Google authorization.

## Outcome

Local Google authorization is removed; remote worksheets are retained.
