---
{
  "entities": [
    {
      "entity": "creator",
      "shows": [
        "Identity",
        "Name",
        "Country",
        "Language",
        "Content category",
        "Biography",
        "Contact details",
        "Archive time"
      ],
      "collects": [
        "Contact details",
        "Country",
        "Language",
        "Content category",
        "Agency association"
      ]
    },
    {
      "entity": "creator-account",
      "shows": [
        "Canonical identity",
        "Platform",
        "Profile identity",
        "Username",
        "Creator association",
        "Account email",
        "Followers",
        "Latest post",
        "Capture status",
        "Capture time",
        "Source",
        "Notes"
      ],
      "collects": [
        "Creator association",
        "Account email"
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
    }
  ]
}
---

# Creator Account Capture

Temporary profile/content analysis, lookup, import preview, linking, progress, uncertainty and redacted diagnostics.
