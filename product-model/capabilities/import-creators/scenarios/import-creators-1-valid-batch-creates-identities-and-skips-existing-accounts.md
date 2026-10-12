---
{
  "kind": "primary",
  "routes": {
    "offered": "Creator Library"
  },
  "steps": [
    {
      "text": "Supply the import workbook for validation.",
      "kind": "actor",
      "actor": "local-user",
      "entities": [],
      "contexts": {
        "offered": {
          "place": "kolconnect-desktop::creator-library"
        }
      }
    },
    {
      "text": "The valid batch creates new canonical profiles/accounts and reports already-existing account identities as skipped.",
      "kind": "product",
      "actor": "local-user",
      "entities": [
        {
          "entity": "creator",
          "effect": "creates",
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
            "Linked review task",
            "Creation time"
          ],
          "to": "Active"
        },
        {
          "entity": "creator-account",
          "effect": "creates",
          "facts": [
            "Canonical identity",
            "Platform",
            "Profile identity",
            "Username",
            "Creator association",
            "Account email",
            "Followers",
            "Latest post",
            "Capture status",
            "Capture time",
            "Source",
            "Notes"
          ],
          "with": "creator"
        }
      ],
      "contexts": {
        "offered": {
          "place": "kolconnect-desktop::creator-library"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "webapp/pages/creator-library.js"
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
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/creator_batch_import.py"
    }
  ]
}
---

# Valid batch creates identities and skips existing Accounts

## Trigger

Supply the import workbook for validation.

## Outcome

The valid batch creates new canonical profiles/accounts and reports already-existing account identities as skipped.
