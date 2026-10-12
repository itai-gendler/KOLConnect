---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "browse-mail-accounts",
      "contexts": [
        {
          "place": "kolconnect-desktop::mail-accounts"
        }
      ]
    },
    {
      "type": "capability",
      "id": "add-mail-account",
      "contexts": [
        {
          "place": "kolconnect-desktop::mail-accounts"
        }
      ]
    },
    {
      "type": "capability",
      "id": "edit-mail-account",
      "contexts": [
        {
          "place": "kolconnect-desktop::mail-accounts"
        }
      ]
    },
    {
      "type": "capability",
      "id": "test-mail-account",
      "contexts": [
        {
          "place": "kolconnect-desktop::mail-accounts"
        }
      ]
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

# Mail credentials are protected and disclosure is masked

Secrets use native Keychain/DPAPI protection where supported and are disclosed masked. A masked save preserves the existing secret. Connection tests check IMAP/SMTP without sending; errors are sanitized.
