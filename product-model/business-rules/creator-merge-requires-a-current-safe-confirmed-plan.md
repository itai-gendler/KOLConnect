---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "merge-creators",
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
      "target": "webapp/pages/creator-library-detail.js"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "webapp/pages/creator-merge.js"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/services/creator_merge_service.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/repositories/creator_merge_repository.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/repositories/creator_merge_repository.py#_apply"
    }
  ]
}
---

# Creator merge requires a current safe confirmed plan

Merge requires explicit confirmation of the current safe plan, retains primary canonical identity and removes the secondary only after conflict checks. Colliding participation and incompatible/stale plans prevent execution; historical reassociation does not edit commercial history.

Merge reassigns the secondary account, capture, video, historical-cooperation and campaign-participation Creator associations. It preserves the primary Creator profile fields and existing snapshot identities.
