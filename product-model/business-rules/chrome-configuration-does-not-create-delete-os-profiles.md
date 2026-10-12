---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "add-chrome-configuration",
      "contexts": [
        {
          "place": "kolconnect-desktop::chrome-accounts"
        }
      ]
    },
    {
      "type": "capability",
      "id": "edit-chrome-configuration",
      "contexts": [
        {
          "place": "kolconnect-desktop::chrome-accounts"
        }
      ]
    },
    {
      "type": "capability",
      "id": "remove-chrome-configuration",
      "contexts": [
        {
          "place": "kolconnect-desktop::chrome-accounts"
        }
      ]
    },
    {
      "type": "capability",
      "id": "open-chrome-profile",
      "contexts": [
        {
          "place": "kolconnect-desktop::chrome-accounts"
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
    }
  ]
}
---

# Chrome configuration does not create/delete OS profiles

Configuration add/edit/remove changes saved aliases/notes for discovered browser profiles. It does not create or delete operating-system profiles; opening requires current profile availability.
