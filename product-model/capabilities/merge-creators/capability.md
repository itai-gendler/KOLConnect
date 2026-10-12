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
    }
  ],
  "domain": "creator-library"
}
---

# Merge Creators

Preview conflicts and confirm a fresh safe merge into a surviving primary profile. Account ownership conflicts offer this entry from detail; conflicting campaign membership or stale plans prevent execution.
