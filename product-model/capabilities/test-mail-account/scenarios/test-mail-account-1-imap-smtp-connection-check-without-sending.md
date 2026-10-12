---
{
  "kind": "primary",
  "routes": {
    "offered": "Mail Accounts"
  },
  "steps": [
    {
      "text": "Request IMAP/SMTP authentication and connectivity checks.",
      "kind": "actor",
      "actor": "local-user",
      "entities": [],
      "contexts": {
        "offered": {
          "place": "kolconnect-desktop::mail-accounts"
        }
      }
    },
    {
      "text": "IMAP/SMTP authentication and connectivity are checked without sending any message.",
      "kind": "product",
      "actor": "local-user",
      "entities": [
        {
          "entity": "mail-account",
          "effect": "reads",
          "facts": [
            "Configuration identity",
            "Mailbox identity",
            "Provider",
            "Connection endpoints",
            "Usernames",
            "Sender details",
            "Enabled",
            "Protected credentials"
          ]
        }
      ],
      "contexts": {
        "offered": {
          "place": "kolconnect-desktop::mail-accounts"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "webapp/pages/settings.js"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/http_handlers/settings_handler.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/services/mail_auth_service.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/services/mail_secret_storage.py"
    }
  ]
}
---

# IMAP/SMTP connection check without sending

## Trigger

Request IMAP/SMTP authentication and connectivity checks.

## Outcome

IMAP/SMTP authentication and connectivity are checked without sending any message.
