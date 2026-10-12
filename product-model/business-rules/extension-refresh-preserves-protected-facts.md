---
{
  "appliesTo": [
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
      "target": "app/services/extension_update_policy.py"
    }
  ]
}
---

# Extension refresh preserves protected facts

Extension UPDATE retains account canonical identity/platform/owner and manual account notes/attribution. Existing Creator name, email, biography, country, language, category, WhatsApp and other already-filled profile facts are fill-only; manual business/cooperation state, owner, notes, tags, archive and associations are retained. Observed mutable account profile/username/followers/latest-post facts can refresh. Existing conflicting account email, current videos and current insights are preserved.
