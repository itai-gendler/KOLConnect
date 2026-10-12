---
{
  "kind": "validation",
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
      "text": "Invalid required profile facts are refused without saving the proposed values.",
      "kind": "product",
      "actor": "local-user",
      "entities": [
        {
          "entity": "creator",
          "effect": "reads",
          "facts": [
            "Identity",
            "Name",
            "Country",
            "Language",
            "Content category",
            "Biography",
            "Contact details",
            "Tags",
            "Notes",
            "Descriptive owner",
            "Agency association",
            "Contact association",
            "Business status",
            "Archive time",
            "Update time",
            "Linked review task"
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

# Invalid required facts refused

## Trigger

Supply supported name, country, language, contact, category and biography edits.

## Outcome

Invalid required profile facts are refused without saving the proposed values.

## Edge cases

- The Contact details input in this form changes WhatsApp; it does not directly edit the recorded email.
- Archived detail disables this profile-edit entry until the separate restore operation clears the archive marker.
