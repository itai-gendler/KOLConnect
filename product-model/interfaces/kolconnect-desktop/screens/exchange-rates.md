---
{
  "entities": [
    {
      "entity": "exchange-rate-settings",
      "shows": [
        "Manual rates",
        "Rate update times"
      ],
      "collects": [
        "Manual rates"
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

# Exchange Rates

Manual rates, update times and USD calculation

 rates and calculator inputs.
