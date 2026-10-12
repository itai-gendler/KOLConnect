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
      "text": "Conflicting account email is preserved while other eligible observed account/profile facts and capture history can update.",
      "kind": "product",
      "actor": "local-user",
      "entities": [
        {
          "entity": "manual-task",
          "effect": "creates",
          "facts": [
            "Task identity",
            "Name",
            "Original inputs",
            "Manual account facts",
            "Confirmed fields",
            "Source/contact linkage",
            "Supplementation scope",
            "Lifecycle",
            "Control requests",
            "Progress",
            "Run summary",
            "Artifacts",
            "Import linkage",
            "Retry scope"
          ],
          "to": "Manual created"
        },
        {
          "entity": "task-result",
          "effect": "creates",
          "facts": [
            "Task/account identity",
            "Capture facts",
            "Capture status",
            "Capture error",
            "Confirmed edits",
            "Review decision",
            "Review reason",
            "Review time",
            "Creator import linkage",
            "Account import linkage"
          ],
          "to": "Pending",
          "with": "manual-task"
        },
        {
          "entity": "creator-account",
          "effect": "changes",
          "facts": [
            "Profile identity",
            "Username",
            "Followers",
            "Latest post",
            "Capture status",
            "Capture time",
            "Source"
          ]
        },
        {
          "entity": "creator",
          "effect": "changes",
          "facts": [
            "Name",
            "Country",
            "Language",
            "Content category",
            "Biography",
            "Contact details",
            "Update time"
          ]
        },
        {
          "entity": "creator-snapshot",
          "effect": "creates",
          "facts": [
            "Capture identity",
            "Source task",
            "Creator association",
            "Observed account",
            "Observed metrics",
            "Score",
            "Level",
            "Capture time",
            "Source"
          ]
        },
        {
          "entity": "video-snapshot",
          "effect": "creates",
          "facts": [
            "Observation identity",
            "Snapshot association",
            "Content identity",
            "Content URL",
            "Platform",
            "Available metrics",
            "Capture time",
            "Creator association"
          ],
          "with": "creator-snapshot"
        }
      ],
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

# Conflicting email preserved

## Trigger

Choose explicit refresh of the existing canonical platform identity.

## Outcome

Conflicting account email is preserved while other eligible observed account/profile facts and capture history can update.
