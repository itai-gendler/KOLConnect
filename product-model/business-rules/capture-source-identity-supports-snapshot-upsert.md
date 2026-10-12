---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "creator-snapshot",
      "effect": "creates"
    },
    {
      "type": "entity",
      "id": "creator-snapshot",
      "effect": "changes",
      "facts": [
        "Capture identity",
        "Source task",
        "Observed account",
        "Observed metrics"
      ]
    },
    {
      "type": "entity",
      "id": "video-snapshot",
      "effect": "creates"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/creator_repository.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/storage/sqlite_creator_repository.py"
    }
  ]
}
---

# Capture source identity supports snapshot upsert

The source task/account capture identity supports upsert of the same Creator Snapshot and its source observations. A new source identity creates history; an existing source identity can update its retained observations.
