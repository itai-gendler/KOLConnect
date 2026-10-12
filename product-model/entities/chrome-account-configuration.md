---
{
  "domain": "chrome-accounts",
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "webapp/pages/settings.js"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/http_handlers/settings_handler.py"
    }
  ]
}
---

# Chrome Account Configuration

Saved configuration for one discovered browser profile, distinct from the operating-system profile itself.

## Information kept

- **Discovered profile identity** — Identity of the discovered operating-system browser profile.
- **Availability** — Current discovered-profile availability.
- **Alias** — Saved configuration alias.
- **Notes** — Saved configuration notes.
