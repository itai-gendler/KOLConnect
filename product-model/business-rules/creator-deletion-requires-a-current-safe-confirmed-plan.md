---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "delete-creator",
      "contexts": [
        {
          "place": "kolconnect-desktop::creator-library"
        }
      ]
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
  ]
}
---

# Creator deletion requires a current safe confirmed plan

Destructive deletion requires an explicit confirmation of a current blocker-free plan. Stale/conflicting plans are refused; staged local failures roll back. A committed local deletion can still have pending cleanup/remote status, which must be disclosed.
