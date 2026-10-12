---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "sync-campaign-report-to-google-sheets",
      "contexts": [
        {
          "place": "kolconnect-desktop::campaign-detail"
        }
      ]
    },
    {
      "type": "capability",
      "id": "sync-creator-data-to-google-sheets",
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
      "target": "webapp/pages/campaign-detail.js"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/http_handlers/campaign_handler.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/services/campaign_creator_service.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/services/campaign_execution_service.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/domain/publication.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/services/google_campaign_report_service.py"
    },
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

# Google replacement protects unmanaged outputs

Google replacement is limited to managed inventory/report outputs; unmanaged inventory targets are refused. Completed remote replacement effects survive later remote failure.
