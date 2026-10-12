---
{
  "domain": "campaigns",
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

# Campaign Brief

The retained content requirements of one Campaign, used for human review and deterministic first-pass checks.

## Information kept

- **Campaign association** — Campaign whose content requirements this brief describes.
- **Title** — Brief title.
- **Selling points** — Selling points.
- **Required content** — Required expressions or content.
- **Forbidden content** — Forbidden expressions or content.
- **Brand requirements** — Brand-specific requirements.
- **Content requirements** — Content-specific requirements.
- **Publication requirements** — Publication-specific requirements.
- **References** — Supporting reference information.
- **Platform guidance** — Platform-specific guidance.
