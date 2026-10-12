---
{
  "appliesTo": [
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
      "id": "reject-task-result",
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

# Review obeys eligibility and transition conflicts

Eligibility and review-transition conflicts are checked separately from capture status. Approval of a rejected result and rejection of an approved result conflict. Repeated decisions retain the existing decision; combined edit/approve rejects an already-approved result.
