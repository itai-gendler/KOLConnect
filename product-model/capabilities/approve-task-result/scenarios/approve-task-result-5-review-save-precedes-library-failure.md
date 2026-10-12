---
{
  "kind": "edge",
  "routes": {
    "offered": "Review Results"
  },
  "steps": [
    {
      "text": "Request approval of the selected eligible result.",
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
      "text": "Approval remains persisted when the subsequent canonical library mutation fails.",
      "kind": "product",
      "actor": "local-user",
      "entities": [
        {
          "entity": "task-result",
          "effect": "changes",
          "facts": [
            "Review decision",
            "Review time"
          ],
          "from": "Pending",
          "to": "Approved"
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
        },
        {
          "entity": "current-video",
          "effect": "reads",
          "facts": [
            "Content identity",
            "Creator association",
            "Content URL",
            "Available views",
            "Available likes",
            "Available comments",
            "Capture time"
          ]
        },
        {
          "entity": "video-snapshot",
          "effect": "reads",
          "facts": [
            "Observation identity",
            "Snapshot association",
            "Content identity",
            "Content URL",
            "Platform",
            "Available metrics",
            "Capture time"
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

# Review save precedes library failure

## Trigger

Request approval of the selected eligible result.

## Outcome

Approval remains persisted when the subsequent canonical library mutation fails.
