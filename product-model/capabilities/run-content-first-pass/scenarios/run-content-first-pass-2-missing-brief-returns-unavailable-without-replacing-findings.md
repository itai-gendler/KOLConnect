---
{
  "kind": "edge",
  "routes": {
    "offered": "Campaign Detail"
  },
  "steps": [
    {
      "text": "Request the deterministic first pass for the selected submitted reference.",
      "kind": "actor",
      "actor": "local-user",
      "entities": [],
      "contexts": {
        "offered": {
          "place": "kolconnect-desktop::campaign-detail"
        }
      }
    },
    {
      "text": "Without a configured brief, first pass returns unavailable and leaves prior findings and human review unchanged.",
      "kind": "product",
      "actor": "local-user",
      "entities": [
        {
          "entity": "content-submission",
          "effect": "reads",
          "facts": [
            "Submission identity",
            "Cooperation association",
            "Optional Account",
            "Content type",
            "Content reference",
            "Submission time",
            "Submitted by",
            "Source",
            "Human review",
            "Review note",
            "First-pass findings"
          ]
        },
        {
          "entity": "campaign-brief",
          "effect": "reads",
          "facts": [
            "Campaign association",
            "Title",
            "Selling points",
            "Required content",
            "Forbidden content",
            "Brand requirements",
            "Content requirements",
            "Publication requirements",
            "References",
            "Platform guidance"
          ]
        }
      ],
      "contexts": {
        "offered": {
          "place": "kolconnect-desktop::campaign-detail"
        }
      }
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
    }
  ]
}
---

# Missing Brief returns unavailable without replacing findings

## Trigger

Request the deterministic first pass for the selected submitted reference.

## Outcome

Without a configured brief, first pass returns unavailable and leaves prior findings and human review unchanged.
