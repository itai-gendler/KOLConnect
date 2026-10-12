---
{
  "kind": "edge",
  "routes": {
    "offered": "Creator Account Capture"
  },
  "steps": [
    {
      "text": "Request bounded recent-content analysis for the current supported profile.",
      "kind": "actor",
      "actor": "local-user",
      "entities": [],
      "contexts": {
        "offered": {
          "place": "kolconnect-chrome-extension::creator-account-capture"
        }
      }
    },
    {
      "text": "Partial, empty or timed-out collection returns qualified available observations rather than fabricated completeness.",
      "kind": "product",
      "actor": "local-user",
      "entities": [],
      "contexts": {
        "offered": {
          "place": "kolconnect-chrome-extension::creator-account-capture"
        }
      }
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
    }
  ]
}
---

# Partial/empty/timeout qualified

## Trigger

Request bounded recent-content analysis for the current supported profile.

## Outcome

Partial, empty or timed-out collection returns qualified available observations rather than fabricated completeness.
