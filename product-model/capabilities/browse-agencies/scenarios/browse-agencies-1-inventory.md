---
{
  "kind": "primary",
  "routes": {
    "offered": "Agencies"
  },
  "steps": [
    {
      "text": "Request the organization inventory or selected organization's related detail.",
      "kind": "actor",
      "actor": "local-user",
      "entities": [],
      "contexts": {
        "offered": {
          "place": "kolconnect-desktop::agencies"
        }
      }
    },
    {
      "text": "Agency inventory and its available reference summaries are returned.",
      "kind": "product",
      "actor": "local-user",
      "entities": [
        {
          "entity": "agency",
          "effect": "reads",
          "facts": [
            "Identity",
            "Name",
            "Country",
            "Website",
            "Contact details",
            "Cooperation stage",
            "Descriptive owner",
            "Tags",
            "Notes",
            "Resources",
            "Follow-up times"
          ]
        },
        {
          "entity": "agency-contact",
          "effect": "reads",
          "facts": [
            "Identity",
            "Agency association",
            "Name",
            "Position",
            "Addresses",
            "Language",
            "Status",
            "Descriptive owner",
            "Notes",
            "Follow-up times",
            "Source"
          ]
        },
        {
          "entity": "creator",
          "effect": "reads",
          "facts": [
            "Identity",
            "Name",
            "Country",
            "Language",
            "Content category",
            "Biography",
            "Contact details",
            "Tags",
            "Notes",
            "Descriptive owner",
            "Agency association",
            "Contact association",
            "Business status",
            "Archive time",
            "Update time",
            "Linked review task"
          ]
        },
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
        }
      ],
      "contexts": {
        "offered": {
          "place": "kolconnect-desktop::agencies"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "webapp/pages/agencies.js"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/services/agency_service.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/storage/sqlite_agency_repository.py"
    }
  ]
}
---

# Inventory

## Trigger

Request the organization inventory or selected organization's related detail.

## Outcome

Agency inventory and its available reference summaries are returned.
