---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "creator",
      "facts": [
        "Identity"
      ],
      "contexts": [
        {
          "place": "kolconnect-desktop::creator-library"
        },
        {
          "place": "kolconnect-desktop::creator-detail"
        },
        {
          "place": "kolconnect-chrome-extension::creator-account-capture"
        }
      ]
    },
    {
      "type": "entity",
      "id": "creator-account",
      "facts": [
        "Canonical identity",
        "Creator association"
      ],
      "contexts": [
        {
          "place": "kolconnect-desktop::creator-detail"
        },
        {
          "place": "kolconnect-chrome-extension::creator-account-capture"
        }
      ]
    },
    {
      "type": "context",
      "context": {
        "place": "feishu-chat-assistant"
      }
    }
  ],
  "references": [
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

# Creator and account identity are distinct

A Creator is the canonical person/business subject; a Creator Account is a platform identity. Lookup and selection must keep those identities distinct rather than treat a platform handle as the canonical person.
