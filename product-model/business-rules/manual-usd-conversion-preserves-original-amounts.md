---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "change-data-settings",
      "contexts": [
        {
          "place": "kolconnect-desktop::data-location"
        },
        {
          "place": "kolconnect-desktop::exchange-rates"
        },
        {
          "place": "kolconnect-desktop::campaign-detail"
        }
      ]
    },
    {
      "type": "capability",
      "id": "convert-money-to-usd",
      "contexts": [
        {
          "place": "kolconnect-desktop::exchange-rates"
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
      "target": "app/http_handlers/settings_handler.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/services/workbook_backup_service.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/services/fx_service.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/domain/money.py"
    },
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
    }
  ]
}
---

# Manual USD conversion preserves original amounts

USD reference conversion divides original amount by manual units-per-USD; USD is one and supplied USD edits are ignored. Missing/invalid rates remain unavailable. Saves accept only supported finite positive rates; earlier entries can mutate memory before a later invalid entry prevents final persistence.
