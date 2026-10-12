---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "campaign-creator",
      "effect": "reads",
      "facts": [
        "Cooperation stage",
        "Due date",
        "Last progress time",
        "Waiting on",
        "Decision needed"
      ],
      "contexts": [
        {
          "place": "kolconnect-desktop::workbench"
        },
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
      "target": "app/services/campaign_execution_service.py"
    }
  ]
}
---

# Execution flags follow inspected predicates

Terminal completed/cancelled/rejected execution stages are not due/overdue/stalled. Nonterminal due-soon means today through two days ahead; overdue means before today; stalled means at least three days since parsed progress/update date, with malformed date falling back to current day.
