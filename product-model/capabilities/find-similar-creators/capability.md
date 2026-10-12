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
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/services/similar_creator_search_service.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/services/creator_similarity_engine.py"
    }
  ],
  "domain": "creator-library"
}
---

# Find similar Creators

Rank candidate profiles using available stored evidence and disclose match reasons; sparse evidence produces qualified or empty candidates.
