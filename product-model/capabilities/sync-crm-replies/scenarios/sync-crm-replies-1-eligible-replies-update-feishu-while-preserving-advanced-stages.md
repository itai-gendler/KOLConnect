---
{
  "kind": "primary",
  "routes": {
    "offered": "Mail"
  },
  "steps": [
    {
      "text": "Request synchronization of eligible observed replies to Feishu.",
      "kind": "actor",
      "actor": "local-user",
      "entities": [],
      "contexts": {
        "offered": {
          "place": "kolconnect-desktop::mail"
        }
      }
    },
    {
      "text": "Eligible matched replies update Feishu and record outcomes while preserving advanced remote cooperation stages.",
      "kind": "product",
      "actor": "local-user",
      "entities": [
        {
          "entity": "mail-message",
          "effect": "changes",
          "facts": [
            "CRM-sync outcome"
          ]
        },
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
        },
        {
          "entity": "feishu-settings",
          "effect": "reads",
          "facts": [
            "Connector identifiers",
            "Protected secret",
            "Target tables",
            "Chat enabled",
            "Configuration status",
            "Transport status"
          ]
        }
      ],
      "contexts": {
        "offered": {
          "place": "kolconnect-desktop::mail"
        }
      }
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
    }
  ]
}
---

# Eligible replies update Feishu while preserving advanced stages

## Trigger

Request synchronization of eligible observed replies to Feishu.

## Outcome

Eligible matched replies update Feishu and record outcomes while preserving advanced remote cooperation stages.
