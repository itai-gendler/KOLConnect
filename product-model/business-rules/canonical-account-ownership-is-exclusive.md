---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "add-creator-account",
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
      "type": "capability",
      "id": "link-account-to-existing-creator",
      "contexts": [
        {
          "place": "kolconnect-chrome-extension::creator-account-capture"
        }
      ]
    },
    {
      "type": "capability",
      "id": "refresh-captured-account",
      "contexts": [
        {
          "place": "kolconnect-chrome-extension::creator-account-capture"
        }
      ]
    },
    {
      "type": "entity",
      "id": "creator-account",
      "effect": "creates",
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
      "type": "entity",
      "id": "creator-account",
      "effect": "changes",
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
      "target": "chrome_extension/content/floating_assistant.js"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "chrome_extension/core/analysis_session.js"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "chrome_extension/core/content_analysis.js"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "chrome_extension/core/diagnostics.js"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "chrome_extension/services/local_api.js"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/server.py#import_extension_capture"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/services/extension_update_policy.py"
    }
  ]
}
---

# Canonical Account ownership is exclusive

A canonical account has one owner. Adding/linking/refreshing does not silently transfer it to another Creator. Same-owner linking is idempotent; conflicting or ambiguous ownership requires an explicit resolution such as the separately offered merge.
