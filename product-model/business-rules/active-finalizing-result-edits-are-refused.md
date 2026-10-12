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

# Active/finalizing result edits are refused

Active or Finalizing task work prevents result edits and the combined edit/approve operation. Invalid supported fields are rejected before the intended result save.

The result validator accepts only name, account name, email, follower, WhatsApp and note fields. Desktop inline save collects email/followers/WhatsApp/notes; the combined review form also collects Creator name. Unknown fields, no changed value, malformed email, unparseable follower input and WhatsApp outside seven-to-twenty digits are refused.
