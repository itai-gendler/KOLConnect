---
{
  "kind": "validation",
  "routes": {
    "offered": "Google Sheets Integration"
  },
  "steps": [
    {
      "text": "Request replacement of managed canonical inventory sheets.",
      "kind": "actor",
      "actor": "local-user",
      "entities": [],
      "contexts": {
        "offered": {
          "place": "kolconnect-desktop::google-sheets-integration"
        }
      }
    },
    {
      "text": "An unmanaged target is refused before replacement.",
      "kind": "product",
      "actor": "local-user",
      "entities": [
        {
          "entity": "google-sheets-settings",
          "effect": "reads",
          "facts": [
            "Client configuration",
            "Target configuration",
            "Local OAuth authorization",
            "Connection status"
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
          "entity": "creator-account",
          "effect": "reads",
          "facts": [
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
        }
      ],
      "contexts": {
        "offered": {
          "place": "kolconnect-desktop::google-sheets-integration"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "webapp/pages/settings.js"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/http_handlers/google_sheets_handler.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/services/google_sheets_data_sync_service.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/google_sheets_client.py"
    }
  ]
}
---

# Unmanaged target refused

## Trigger

Request replacement of managed canonical inventory sheets.

## Outcome

An unmanaged target is refused before replacement.
