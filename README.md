# opsforge-windows-middleware

Windows and middleware health checks and service operations.

> **Status: not started — scaffold only.** This repository reserves the structure for the automation and records its intended scope. It contains no working code yet, and nothing here has been tested or run against any infrastructure.

Part of the [OpsForge](https://github.com/NPKpadala/opsforge-core) family. Reference implementation to copy the layout from: [opsforge-linux-health](https://github.com/NPKpadala/opsforge-linux-health).

## Planned scope

- Windows service/disk/event-log checks
- Middleware (IIS/app-server) health
- Approval-gated service restarts

## Design rules (shared by every OpsForge automation)

- Depends on a pinned `opsforge-core` release; plugin registered via the `opsforge.plugins` entry point.
- Real adapter boundary (WinRM) that is mocked in CI; no static fake results.
- YAML configuration, `env:` credential references, secret redaction, JSON audit trail, retries, JSON reports.
- Change workflow: DETECT → EVIDENCE → PLAN → APPROVAL → EXECUTE → VERIFY → ROLLBACK (or explicit limitation) → AUDIT → REPORT; dry-run proven by tests to make no change.

## Implementation matrix

| Area | Implemented | Tests | Dry-run | Reporting | Real-infra verified |
|---|---|---|---|---|---|
| Collection adapter | no | no | n/a | no | no |
| Evaluation | no | no | n/a | no | no |
| Reporting | no | no | n/a | no | no |
| Change workflow + rollback | no | no | no | no | no |
| Packaging / CI / Docker | no | no | n/a | n/a | no |

## License

MIT
