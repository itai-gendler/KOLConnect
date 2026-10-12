---
{
  "kind": "edge",
  "routes": {
    "offered": "Creator Account Capture"
  },
  "steps": [
    {
      "text": "Request analysis of the current supported public profile.",
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
      "text": "Unsupported, incomplete or failed profile evidence returns unavailable/qualified outcome without canonical mutation.",
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
    }
  ]
}
---

# Unsupported/incomplete/failed profile unavailable

## Trigger

Request analysis of the current supported public profile.

## Outcome

Unsupported, incomplete or failed profile evidence returns unavailable/qualified outcome without canonical mutation.
