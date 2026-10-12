---
{
  "availability": [
    {
      "place": "kolconnect-desktop"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "webapp/pages/creator-library.js"
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
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/services/creator_hard_delete_service.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/services/creator_delete_plan.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/repositories/creator_hard_delete_repository.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/staged_delete_transaction.py"
    }
  ],
  "domain": "creator-library"
}
---

# Delete Creator

Preview and explicitly confirm a current safe deletion plan. Local staged deletion may roll back; after a local commit, external cleanup can remain pending and is disclosed.
