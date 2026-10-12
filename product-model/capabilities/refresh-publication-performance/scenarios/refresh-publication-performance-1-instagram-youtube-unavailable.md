---
{
  "kind": "edge",
  "routes": {
    "offered": "Campaign Detail"
  },
  "steps": [
    {
      "text": "Select an actual record or eligible batch and request metric refresh.",
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
      "text": "Instagram/YouTube production refresh returns unavailable and appends no successful observation.",
      "kind": "product",
      "actor": "local-user",
      "entities": [
        {
          "entity": "campaign",
          "effect": "reads",
          "facts": [
            "Identity",
            "Name",
            "Product association",
            "Country",
            "Target platforms",
            "Start date",
            "End date",
            "Descriptive owner",
            "Budget",
            "Goal",
            "Notes",
            "Business status",
            "Archive time"
          ]
        },
        {
          "entity": "campaign-creator",
          "effect": "reads",
          "facts": [
            "Participation identity",
            "Campaign association",
            "Creator association",
            "Execution Accounts",
            "Cooperation stage",
            "Quote currency",
            "Quote unit amount",
            "Quote quantity",
            "Pricing unit",
            "Quote total",
            "Cost",
            "Cost currency",
            "Planned publication dates",
            "Compatibility publication facts",
            "Recorded metrics",
            "Recorded ROI",
            "Performance notes",
            "Responsibility",
            "Next action",
            "Due date",
            "Waiting on",
            "Decision needed",
            "Last progress time",
            "Archive time"
          ]
        },
        {
          "entity": "actual-publication",
          "effect": "reads",
          "facts": [
            "Publication identity",
            "Cooperation association",
            "Platform",
            "Normalized content URL",
            "Actual Account",
            "Actual publication time",
            "Recording time",
            "Observation time",
            "Provenance"
          ]
        },
        {
          "entity": "publication-performance-observation",
          "effect": "reads",
          "facts": [
            "Observation identity",
            "Publication association",
            "Observation time",
            "Available metrics",
            "Engagement",
            "Source",
            "Confidence",
            "Refresh provenance"
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
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/services/publication_tracking_service.py"
    }
  ]
}
---

# Instagram/YouTube unavailable

## Trigger

Select an actual record or eligible batch and request metric refresh.

## Outcome

Instagram/YouTube production refresh returns unavailable and appends no successful observation.
