---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "record-actual-publication",
      "contexts": [
        {
          "place": "kolconnect-desktop::campaign-detail"
        }
      ]
    },
    {
      "type": "capability",
      "id": "edit-actual-publication",
      "contexts": [
        {
          "place": "kolconnect-desktop::campaign-detail"
        }
      ]
    },
    {
      "type": "entity",
      "id": "actual-publication",
      "effect": "creates",
      "facts": [
        "Actual Account"
      ]
    },
    {
      "type": "entity",
      "id": "actual-publication",
      "effect": "changes",
      "facts": [
        "Actual Account"
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
      "target": "app/repositories/publication_performance_repository.py"
    }
  ]
}
---

# Actual publication Account belongs to its Creator

A supplied actual publication account must belong to the participation's canonical Creator. It need not belong to planned execution selection or campaign target platforms.
