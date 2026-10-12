---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "sync-inbox",
      "contexts": [
        {
          "place": "kolconnect-desktop::mail"
        }
      ]
    },
    {
      "type": "capability",
      "id": "sync-crm-replies",
      "contexts": [
        {
          "place": "kolconnect-desktop::mail"
        }
      ]
    },
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
      "target": "webapp/app.js"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/mail_sync.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/services/mail_inbox_facts.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/http_handlers/settings_handler.py"
    },
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

# Mail matching distinguishes Account multiplicity from Creator ambiguity

Address matching uses exact normalized account-address evidence. Multiple matching accounts of one canonical Creator are not the same as multiple matching Creators; ambiguous Creator evidence cannot choose an arbitrary target.
