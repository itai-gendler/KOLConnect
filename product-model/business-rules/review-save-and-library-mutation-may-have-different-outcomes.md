---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "edit-task-result",
      "contexts": [
        {
          "place": "kolconnect-desktop::review-results"
        }
      ]
    },
    {
      "type": "capability",
      "id": "approve-task-result",
      "contexts": [
        {
          "place": "kolconnect-desktop::review-results"
        }
      ]
    },
    {
      "type": "capability",
      "id": "edit-and-approve-task-result",
      "contexts": [
        {
          "place": "kolconnect-desktop::review-results"
        }
      ]
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

# Review save and library mutation may have different outcomes

Confirmed edits or review decisions can persist before subsequent canonical-library mutation fails. A later failure must disclose the preceding successful result/review save rather than claim the whole run rolled back.
