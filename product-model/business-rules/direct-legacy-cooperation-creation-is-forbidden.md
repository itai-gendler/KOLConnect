---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "legacy-cooperation",
      "effect": "creates",
      "contexts": [
        {
          "place": "kolconnect-desktop::creator-library"
        },
        {
          "place": "kolconnect-desktop::creator-detail"
        }
      ]
    }
  ],
  "permits": [],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/http_handlers/creator_handler.py"
    }
  ]
}
---

# Direct Legacy Cooperation creation is forbidden

No direct creation of Legacy Cooperation is offered or performed in the Creator Library/detail operation contexts. Dependent records going with another permitted operation are governed with their parent.
