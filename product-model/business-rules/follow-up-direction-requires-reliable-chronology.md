---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "browse-mail-follow-up",
      "contexts": [
        {
          "place": "kolconnect-desktop::mail-follow-up"
        }
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "webapp/pages/mail-follow-up.js"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/services/mail_follow_up.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/services/mail_follow_up_preferences.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/http_handlers/mail_follow_up_handler.py"
    }
  ]
}
---

# Follow-up direction requires reliable chronology

Waiting direction is derived only from reliable bounded inbound/outbound chronology; partial or unknown history must be qualified and never claimed lifetime-complete.

The current grouping query excludes legacy Creator status values archived and rejected. It does not test the separate archive-time marker in that exclusion predicate.
