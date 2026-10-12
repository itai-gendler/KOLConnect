---
{
  "entities": [
    {
      "entity": "creator",
      "shows": [
        "Identity",
        "Name",
        "Country",
        "Language",
        "Content category",
        "Contact details",
        "Business status",
        "Archive time",
        "Agency association",
        "Linked review task"
      ]
    },
    {
      "entity": "creator-account",
      "shows": [
        "Platform",
        "Profile identity",
        "Followers",
        "Account email",
        "Capture status"
      ]
    },
    {
      "entity": "campaign",
      "shows": [
        "Identity",
        "Name",
        "Target platforms",
        "Archive time"
      ]
    },
    {
      "entity": "campaign-creator",
      "shows": [
        "Campaign association",
        "Creator association",
        "Execution Accounts",
        "Archive time"
      ]
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
    }
  ]
}
---

# Creator Library

Canonical inventory, business status, archive state, account summaries and selection

 import/export and merge/delete previews.
