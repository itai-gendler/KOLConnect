---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "connect-google-sheets",
      "contexts": [
        {
          "place": "kolconnect-desktop::google-sheets-integration"
        }
      ]
    },
    {
      "type": "capability",
      "id": "disconnect-google-sheets",
      "contexts": [
        {
          "place": "kolconnect-desktop::google-sheets-integration"
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

# Google disconnect removes local authorization

Disconnect removes local Google authorization and leaves remote worksheet data. Cancelled/unavailable connection does not create a successful local authorization.
