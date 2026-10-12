---
{
  "kind": "primary",
  "routes": {
    "offered": "Creator Detail"
  },
  "steps": [
    {
      "text": "Select primary and secondary canonical identities and confirm the current safe merge plan.",
      "kind": "actor",
      "actor": "local-user",
      "entities": [],
      "contexts": {
        "offered": {
          "place": "kolconnect-desktop::creator-detail"
        }
      }
    },
    {
      "text": "An account-owner conflict offers detail merge; confirming its current safe plan preserves the selected primary identity.",
      "kind": "product",
      "actor": "local-user",
      "entities": [
        {
          "entity": "creator",
          "effect": "reads",
          "facts": [
            "Contact details",
            "Tags",
            "Notes",
            "Agency association",
            "Contact association",
            "Update time"
          ],
          "as": "primary-creator"
        },
        {
          "entity": "creator-account",
          "effect": "changes",
          "facts": [
            "Creator association"
          ]
        },
        {
          "entity": "creator-snapshot",
          "effect": "changes",
          "facts": [
            "Creator association"
          ]
        },
        {
          "entity": "current-video",
          "effect": "changes",
          "facts": [
            "Creator association"
          ]
        },
        {
          "entity": "video-snapshot",
          "effect": "changes",
          "facts": [
            "Creator association"
          ]
        },
        {
          "entity": "legacy-cooperation",
          "effect": "changes",
          "facts": [
            "Creator association"
          ]
        },
        {
          "entity": "campaign-creator",
          "effect": "changes",
          "facts": [
            "Creator association"
          ]
        },
        {
          "entity": "creator",
          "effect": "removes",
          "as": "secondary-creator",
          "from": "Active"
        }
      ],
      "contexts": {
        "offered": {
          "place": "kolconnect-desktop::creator-detail"
        }
      }
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

# Merge entry following Account-owner conflict

## Trigger

Select primary and secondary canonical identities and confirm the current safe merge plan.

## Outcome

An account-owner conflict offers detail merge; confirming its current safe plan preserves the selected primary identity.


## Edge cases

- A safe plan can merge an archived secondary; the archive marker does not by itself prohibit merge.

- Primary Creator name, contacts, notes, tags, responsibility and Agency/Contact associations remain as recorded; reassociation does not combine these profile values.
- Video Snapshot Creator association moves with the captured history while its Snapshot association and observation identity remain unchanged.
