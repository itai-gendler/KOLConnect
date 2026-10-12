---
{
  "kind": "edge",
  "routes": {
    "offered": "Creator Detail"
  },
  "steps": [
    {
      "text": "Request similar profiles for the selected canonical identity.",
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
      "text": "Insufficient comparison evidence yields qualified or empty matches rather than fabricated similarity.",
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
        },
        {
          "entity": "creator-account",
          "effect": "reads",
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
          ]
        },
        {
          "entity": "creator-snapshot",
          "effect": "reads",
          "facts": [
            "Capture identity",
            "Source task",
            "Creator association",
            "Observed account",
            "Observed metrics",
            "Score",
            "Level",
            "Capture time",
            "Source"
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
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/services/similar_creator_search_service.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/services/creator_similarity_engine.py"
    }
  ]
}
---

# Insufficient evidence gives qualified/empty matches

## Trigger

Request similar profiles for the selected canonical identity.

## Outcome

Insufficient comparison evidence yields qualified or empty matches rather than fabricated similarity.
