---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "legacy-cooperation",
      "effect": "changes",
      "facts": [
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
      ],
      "contexts": [
        {
          "place": "kolconnect-desktop::creator-library"
        },
        {
          "place": "kolconnect-desktop::creator-detail"
        }
      ]
    }
  ],
  "permits": [],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/http_handlers/creator_handler.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/services/creator_merge_service.py"
    }
  ]
}
---

# Direct Legacy Cooperation commercial editing is forbidden

Direct changes to Legacy Cooperation's historical campaign, platform, date, price, counts, results, notes and creation facts are forbidden in Creator Library/detail. Merge may change only its Creator association; that association is outside this commercial selector.
