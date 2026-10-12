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
        "Publication identity",
        "Platform",
        "Normalized content URL"
      ]
    },
    {
      "type": "entity",
      "id": "actual-publication",
      "effect": "changes",
      "facts": [
        "Platform",
        "Normalized content URL"
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

# Normalized publication identity survives repeated recording

Normalized platform/content identity identifies repeated actual recording. Re-recording retains publication identity instead of creating duplicate actual records.
