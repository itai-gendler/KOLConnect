---
{
  "domain": "email-crawl",
  "relations": [
    {
      "entity": "task-result",
      "verb": "contains",
      "cardinality": "one-to-many"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "webapp/app.js"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/http_handlers/task_handler.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/services/task_service.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/adapters/task_manager_adapter.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/repositories/task_repository.py"
    }
  ]
}
---

# Manual Task

An addressed manually initialized capture, optionally supplemented automatically while protecting confirmed facts.

## Information kept

- **Original inputs** — Original retained input links addressed by task add/edit/remove/copy controls.
- **Control requests** — Persisted pause and stop requests for this task family.
- **Task identity** — Addressed manual-capture identity.
- **Name** — Task name.
- **Manual account facts** — Supplied platform-account capture facts.
- **Confirmed fields** — Fields confirmed by manual input and protected during supplementation.
- **Source/contact linkage** — Source and contact linkage of manual input.
- **Supplementation scope** — Selected automatic supplementation scope.
- **Lifecycle** — Current manual capture/supplementation lifecycle.
- **Progress** — Supplementation progress.
- **Run summary** — Execution scope, timing and terminal outcome.
- **Artifacts** — Controlled result artifacts.
- **Import linkage** — Canonical library-import linkage.

- **Retry scope** — Selected failed-input retry links, round and request information retained by shared retry preparation.

## States

### Manual created

Manual capture initialization is complete; supplementation has not started.

### Created

Failed-input retry has reset this existing task family's preparation lifecycle; this is not its initial initialization state.

### Running

The selected work has a running worker.

### Paused

The live worker has reached the pause boundary.

### Interrupted

Work was running but no worker remains; it can be continued where eligible.

### Stopping

Stopping has been requested while a worker remains.

### Stopped

The worker has stopped, or eligible workerless work was stopped directly.

### Finalizing

Capture is complete enough to finalize results and canonical import; concurrent control/mutation is protected.

### Completed

Finalization and supported canonical import have completed.

### Failed

Execution or finalization/import failed and the failure is disclosed.
