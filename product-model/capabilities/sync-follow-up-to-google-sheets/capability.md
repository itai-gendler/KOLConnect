---
{
  "availability": [
    {
      "place": "kolconnect-desktop"
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
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/services/mail_follow_up_google_sheets_replica_service.py"
    }
  ]
}
---

# Sync follow-up to Google Sheets

Upsert managed follow-up rows in Google Sheets and retain stale remote rows; disclose partial remote outcomes.
