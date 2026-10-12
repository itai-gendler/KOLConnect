---
{
  "kind": "validation",
  "routes": {
    "offered": "Exchange Rates"
  },
  "steps": [
    {
      "text": "Supply a source location or manual reference rates in the offered settings context.",
      "kind": "actor",
      "actor": "local-user",
      "entities": [],
      "contexts": {
        "offered": {
          "place": "kolconnect-desktop::exchange-rates"
        }
      }
    },
    {
      "text": "Unsupported, malformed, nonfinite or nonpositive rate input is refused.",
      "kind": "product",
      "actor": "local-user",
      "entities": [
        {
          "entity": "exchange-rate-settings",
          "effect": "reads",
          "facts": [
            "Manual rates",
            "Rate update times"
          ]
        }
      ],
      "contexts": {
        "offered": {
          "place": "kolconnect-desktop::exchange-rates"
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

# Invalid/unsupported/nonpositive rate refused

## Trigger

Supply a source location or manual reference rates in the offered settings context.

## Outcome

Unsupported, malformed, nonfinite or nonpositive rate input is refused.
