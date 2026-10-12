---
{
  "kind": "primary",
  "routes": {
    "offered": "Exchange Rates"
  },
  "steps": [
    {
      "text": "Supply original amount and currency for reference USD conversion.",
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
      "text": "An available supported reference rate produces original amount divided by currency units per USD; USD is unchanged.",
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
      "target": "app/services/fx_service.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/domain/money.py"
    }
  ]
}
---

# Current-rate conversion

## Trigger

Supply original amount and currency for reference USD conversion.

## Outcome

An available supported reference rate produces original amount divided by currency units per USD; USD is unchanged.
