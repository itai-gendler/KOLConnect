---
{
  "kind": "primary",
  "routes": {
    "offered": "Creator Detail"
  },
  "steps": [
    {
      "text": "Supply supported name, country, language, contact, category and biography edits.",
      "kind": "actor",
      "actor": "local-user",
      "entities": [],
      "contexts": {
        "offered": {
          "place": "kolconnect-desktop::creator-detail"
        }
      }
    },
    {
      "text": "Supported name, country, language, contact, category and biography values are saved for the selected profile.",
      "kind": "product",
      "actor": "local-user",
      "entities": [
        {
          "entity": "creator",
          "effect": "changes",
          "facts": [
            "Name",
            "Country",
            "Language",
            "Contact details",
            "Content category",
            "Biography",
            "Update time"
          ]
        }
      ],
      "contexts": {
        "offered": {
          "place": "kolconnect-desktop::creator-detail"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "webapp/pages/creator-library-detail.js"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/services/creator_service.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/storage/sqlite_creator_repository.py"
    }
  ]
}
---

# Save supported name/country/language/contact/category/bio

## Trigger

Supply supported name, country, language, contact, category and biography edits.

## Outcome

Supported name, country, language, contact, category and biography values are saved for the selected profile.

## Edge cases

- The Contact details input in this form changes WhatsApp; it does not directly edit the recorded email.
- Archived detail disables this profile-edit entry until the separate restore operation clears the archive marker.
