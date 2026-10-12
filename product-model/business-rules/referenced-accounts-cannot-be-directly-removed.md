---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "remove-creator-account",
      "contexts": [
        {
          "place": "kolconnect-desktop::creator-detail"
        }
      ]
    },
    {
      "type": "entity",
      "id": "creator-account",
      "effect": "removes",
      "contexts": [
        {
          "place": "kolconnect-desktop::creator-detail"
        }
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "webapp/pages/creator-library-detail.js"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/services/creator_service.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/storage/sqlite_creator_repository.py"
    }
  ]
}
---

# Referenced Accounts cannot be directly removed

Direct account removal is refused when capture history, execution selection or actual-publication association references it. The final unreferenced account may be removed.
