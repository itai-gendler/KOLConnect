---
{
  "entities": [
    {
      "entity": "creator",
      "shows": [
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
      ],
      "collects": [
        "Name",
        "Country",
        "Language",
        "Contact details",
        "Content category",
        "Biography",
        "Agency association"
      ]
    },
    {
      "entity": "creator-account",
      "shows": [
        "Canonical identity",
        "Platform",
        "Profile identity",
        "Username",
        "Creator association",
        "Account email",
        "Followers",
        "Latest post",
        "Capture status",
        "Capture time",
        "Source",
        "Notes"
      ]
    },
    {
      "entity": "creator-snapshot",
      "shows": [
        "Capture identity",
        "Source task",
        "Creator association",
        "Observed account",
        "Observed metrics",
        "Score",
        "Level",
        "Capture time",
        "Source"
      ]
    },
    {
      "entity": "current-video",
      "shows": [
        "Content identity",
        "Creator association",
        "Content URL",
        "Available views",
        "Available likes",
        "Available comments",
        "Capture time"
      ]
    },
    {
      "entity": "video-snapshot",
      "shows": [
        "Observation identity",
        "Snapshot association",
        "Content identity",
        "Content URL",
        "Platform",
        "Available metrics",
        "Capture time"
      ]
    },
    {
      "entity": "legacy-cooperation",
      "shows": [
        "Historical identity",
        "Creator association",
        "Campaign description",
        "Platform",
        "Contact date",
        "Untyped price",
        "Publication count",
        "Recorded views",
        "Recorded ROI",
        "Result",
        "Notes",
        "Creation time"
      ]
    },
    {
      "entity": "campaign",
      "shows": [
        "Identity",
        "Name"
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
      "entity": "agency",
      "shows": [
        "Identity",
        "Name"
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "webapp/pages/creator-library-detail.js"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/services/creator_service.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/storage/sqlite_creator_repository.py"
    }
  ]
}
---

# Creator Detail

Selected Creator, Accounts, snapshots, current videos, legacy cooperation and campaign/performance history

 supported profile facts and associations.
