---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "sync-follow-up-to-google-sheets",
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
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/services/mail_follow_up_google_sheets_replica_service.py"
    }
  ]
}
---

# Follow-up Sheets sync retains stale remote rows

Follow-up Sheets synchronization upserts managed rows without deleting stale remote rows. Partial completed remote effects are disclosed.
