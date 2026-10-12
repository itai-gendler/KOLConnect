---
{
  "domain": "advanced",
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "webapp/pages/settings.js"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/http_handlers/storage_migration_handler.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/services/production_migration_service.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/storage/migration.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/storage/authority.py"
    }
  ]
}
---

# Storage Migration

A particular migration the local operator can inspect, prepare, activate, cancel or recover.

## Information kept

- **Migration identity** — Addressed migration identity.
- **Prepared source** — Prepared legacy source location.
- **Source fingerprint** — Fingerprint used to revalidate the confirmed source.
- **Validation results** — Source/schema/staging validation results.
- **Counts** — Source and staged record counts.
- **Digests** — Validation comparison digests.
- **Backup** — Retained source backup.
- **Staged target** — Prepared SQLite target.
- **Phase** — Current preparation/activation/recovery phase.
- **Timing** — Preparation, activation and terminal timing.
- **Failure** — Recorded failed validation/staging/activation details.
- **Activation result** — Recorded authority activation or commit-point recovery result.

## States

### Preparing

Legacy source validation, backup and SQLite staging are in progress.

### Ready for activation

Validated staging is ready for an addressed confirmation.

### Activation in progress

Activation has begun and commit-point recovery may be required.

### Completed

SQLite activation or post-commit recovery has completed.

### Cancelled

Ready staging was cancelled and its confirmation discarded.

### Failed

Preparation or activation failed; the addressed failure and authority outcome remain inspectable.
