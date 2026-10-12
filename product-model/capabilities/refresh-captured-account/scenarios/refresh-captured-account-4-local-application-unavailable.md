---
{
  "kind": "edge",
  "routes": {
    "offered": "Creator Account Capture"
  },
  "steps": [
    {
      "text": "Choose explicit refresh of the existing canonical platform identity.",
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
      "text": "Local application unavailability prevents a committed refresh and is disclosed.",
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
      "target": "app/services/extension_update_policy.py"
    }
  ]
}
---

# Local application unavailable

## Trigger

Choose explicit refresh of the existing canonical platform identity.

## Outcome

Local application unavailability prevents a committed refresh and is disclosed.
