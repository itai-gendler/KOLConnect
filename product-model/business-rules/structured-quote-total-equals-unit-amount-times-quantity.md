---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "campaign-creator",
      "effect": "creates",
      "facts": [
        "Quote currency",
        "Quote unit amount",
        "Quote quantity",
        "Pricing unit",
        "Quote total"
      ]
    },
    {
      "type": "entity",
      "id": "campaign-creator",
      "effect": "changes",
      "facts": [
        "Quote currency",
        "Quote unit amount",
        "Quote quantity",
        "Pricing unit",
        "Quote total"
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

# Structured quote total equals unit amount times quantity

Currency input is trimmed and uppercased; its normalized form must be exactly three uppercase letters. A structured quote requires this currency, a finite nonnegative unit amount, positive integer quantity and video/post/reel/short/story/package/other unit. Total equals amount times quantity; a contradictory supplied total is refused. Syntax validation does not prove currency-registry membership.
