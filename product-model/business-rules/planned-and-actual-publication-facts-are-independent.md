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
    },
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
      "type": "capability",
      "id": "remove-actual-publication",
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
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/repositories/publication_performance_repository.py"
    }
  ]
}
---

# Planned and actual publication facts are independent

Planned execution accounts/dates do not establish an actual account, time or public URL. Compatibility publish date follows the first planned date where implemented. Actual recording independently retains unknown actual values and multiple actual records.
