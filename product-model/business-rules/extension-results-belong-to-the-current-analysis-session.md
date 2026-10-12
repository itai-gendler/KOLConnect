---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "analyze-profile",
      "contexts": [
        {
          "place": "kolconnect-chrome-extension::creator-account-capture"
        }
      ]
    },
    {
      "type": "capability",
      "id": "analyze-recent-content",
      "contexts": [
        {
          "place": "kolconnect-chrome-extension::creator-account-capture"
        }
      ]
    },
    {
      "type": "capability",
      "id": "cancel-content-analysis",
      "contexts": [
        {
          "place": "kolconnect-chrome-extension::creator-account-capture"
        }
      ]
    },
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
    }
  ],
  "references": [
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
      "target": "chrome_extension/platform/instagram.js"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "chrome_extension/platform/youtube.js"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "chrome_extension/capture/tiktok_capture_session.js"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "chrome_extension/content/tiktok_capture_runtime.js"
    },
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
      "target": "app/services/extension_update_policy.py"
    }
  ]
}
---

# Extension results belong to the current analysis session

Analysis/capture callbacks must belong to the current analysis session. Cancelled or obsolete sessions cannot overwrite the current outcome or apply a stale mutation continuation.
