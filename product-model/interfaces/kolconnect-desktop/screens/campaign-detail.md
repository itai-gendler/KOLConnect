---
{
  "entities": [
    {
      "entity": "campaign",
      "shows": [
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
      "entity": "product",
      "shows": [
        "Identity",
        "Name"
      ]
    },
    {
      "entity": "creator",
      "shows": [
        "Identity",
        "Name"
      ]
    },
    {
      "entity": "creator-account",
      "shows": [
        "Canonical identity",
        "Platform",
        "Profile identity",
        "Username",
        "Creator association"
      ]
    },
    {
      "entity": "campaign-creator",
      "shows": [
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
      ],
      "collects": [
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
        "Decision needed"
      ]
    },
    {
      "entity": "campaign-brief",
      "shows": [
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
      ],
      "collects": [
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
    },
    {
      "entity": "content-submission",
      "shows": [
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
      ],
      "collects": [
        "Optional Account",
        "Content type",
        "Content reference",
        "Human review",
        "Review note"
      ]
    },
    {
      "entity": "actual-publication",
      "shows": [
        "Publication identity",
        "Cooperation association",
        "Platform",
        "Normalized content URL",
        "Actual Account",
        "Actual publication time",
        "Recording time",
        "Observation time",
        "Provenance"
      ],
      "collects": [
        "Platform",
        "Normalized content URL",
        "Actual Account",
        "Actual publication time"
      ]
    },
    {
      "entity": "publication-performance-observation",
      "shows": [
        "Observation identity",
        "Publication association",
        "Observation time",
        "Available metrics",
        "Engagement",
        "Source",
        "Confidence",
        "Refresh provenance"
      ]
    },
    {
      "entity": "exchange-rate-settings",
      "shows": [
        "Manual rates",
        "Rate update times"
      ],
      "collects": [
        "Manual rates"
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
    }
  ]
}
---

# Campaign Detail

Cooperation, execution Accounts, plans, money, brief, submissions, actual publications and observations

 related edits and inline rates.
