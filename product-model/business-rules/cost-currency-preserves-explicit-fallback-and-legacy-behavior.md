---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "campaign-creator",
      "facts": [
        "Cost",
        "Cost currency",
        "Quote currency"
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/domain/money.py"
    }
  ]
}
---

# Cost currency preserves explicit, fallback and legacy behavior

Explicit cost currency is preserved; when cost has no currency and the quote supplies one, the implemented path can use quote currency. A newly supplied explicit empty currency with cost and no quote fallback is refused. Legacy omitted currency can remain unknown.
