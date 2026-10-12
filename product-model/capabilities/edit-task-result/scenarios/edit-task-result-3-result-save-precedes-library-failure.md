---
{
  "kind": "edge",
  "routes": {
    "offered": "Review Results"
  },
  "steps": [
    {
      "text": "Supply supported confirmed-field edits for the selected result.",
      "kind": "actor",
      "actor": "local-user",
      "entities": [],
      "contexts": {
        "offered": {
          "place": "kolconnect-desktop::review-results"
        }
      }
    },
    {
      "text": "The confirmed result edits remain saved when later canonical library synchronization fails.",
      "kind": "product",
      "actor": "local-user",
      "entities": [
        {
          "entity": "task-result",
          "effect": "changes",
          "facts": [
            "Confirmed edits"
          ]
        },
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
        }
      ],
      "contexts": {
        "offered": {
          "place": "kolconnect-desktop::review-results"
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
      "target": "app/services/task_service.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/services/task_result_mapper.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/creator_repository.py"
    }
  ]
}
---

# Result save precedes library failure

## Trigger

Supply supported confirmed-field edits for the selected result.

## Outcome

The confirmed result edits remain saved when later canonical library synchronization fails.
