---
{
  "singleton": true,
  "domain": "data",
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
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/services/fx_service.py#SUPPORTED_CURRENCIES"
    }
  ]
}
---

# Exchange-rate Settings

The product's manual reference conversion settings; they do not replace original commercial currencies.

## Information kept

- **Manual rates** — Manual currency units per USD for USD, CNY, BRL, EUR, GBP, JPY, KRW, HKD, TWD, SGD, AUD, CAD, MXN, SAR, AED, INR, IDR, THB, VND, PHP, MYR, TRY and ZAR; USD remains one.
- **Rate update times** — Time of the last saved rate for each configured currency.
