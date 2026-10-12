---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "legacy-cooperation",
      "effect": "removes",
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
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/services/creator_hard_delete_service.py"
    }
  ]
}
---

# Direct Legacy Cooperation removal is forbidden

Direct removal of Legacy Cooperation in Creator Library/detail is forbidden. Parent-dependent deletion/reset is represented with its enclosing removal and is distinct from this direct operation.
