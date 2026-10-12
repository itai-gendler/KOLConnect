---
{
  "kind": "primary",
  "routes": {
    "offered": "Data Location"
  },
  "steps": [
    {
      "text": "Supply a source location or manual reference rates in the offered settings context.",
      "kind": "actor",
      "actor": "local-user",
      "entities": [],
      "contexts": {
        "offered": {
          "place": "kolconnect-desktop::data-location"
        }
      }
    },
    {
      "text": "The configured source location is saved through the Data Location path.",
      "kind": "product",
      "actor": "local-user",
      "entities": [
        {
          "entity": "data-settings",
          "effect": "changes",
          "facts": [
            "Configured source location"
          ]
        }
      ],
      "contexts": {
        "offered": {
          "place": "kolconnect-desktop::data-location"
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

# Location save

## Trigger

Supply a source location or manual reference rates in the offered settings context.

## Outcome

The configured source location is saved through the Data Location path.
