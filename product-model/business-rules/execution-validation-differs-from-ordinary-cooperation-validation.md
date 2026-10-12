---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "edit-campaign-cooperation",
      "contexts": [
        {
          "place": "kolconnect-desktop::campaign-detail"
        }
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "webapp/pages/campaign-detail.js"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/http_handlers/campaign_handler.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/services/campaign_creator_service.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/services/campaign_execution_service.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/domain/publication.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/domain/money.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/campaign_creator_repository.py"
    }
  ]
}
---

# Execution validation differs from ordinary cooperation validation

Ordinary cooperation validates its shipped stage vocabulary and planned dates. Direct execution accepts trimmed stage text, validates due date and waiting-on creator/internal/client/self/none, coerces the decision flag and updates last progress on meaningful change. The two saves can have different outcomes.
