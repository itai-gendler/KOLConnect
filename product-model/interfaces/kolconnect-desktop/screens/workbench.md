---
{
  "entities": [
    {
      "entity": "creator",
      "shows": [
        "Identity",
        "Name",
        "Business status",
        "Archive time",
        "Contact details",
        "Creation time"
      ]
    },
    {
      "entity": "creator-account",
      "shows": [
        "Platform",
        "Account email",
        "Capture status",
        "Capture time"
      ]
    },
    {
      "entity": "campaign",
      "shows": [
        "Identity",
        "Name",
        "Business status",
        "Archive time",
        "Budget"
      ]
    },
    {
      "entity": "campaign-creator",
      "shows": [
        "Cooperation stage",
        "Cost",
        "Cost currency",
        "Quote total",
        "Quote currency",
        "Planned publication dates",
        "Recorded metrics",
        "Recorded ROI",
        "Next action",
        "Due date",
        "Decision needed",
        "Archive time"
      ]
    },
    {
      "entity": "legacy-cooperation",
      "shows": [
        "Untyped price",
        "Recorded views",
        "Recorded ROI"
      ]
    },
    {
      "entity": "content-submission",
      "shows": [
        "Human review",
        "Content type"
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "webapp/pages/dashboard.js"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/dashboard_service.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/services/campaign_execution_service.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/services/risk_service.py"
    }
  ]
}
---

# Workbench

Creator/account health, campaign/cooperation metrics, currency buckets, recorded ROI, execution actions and risk projections.
