# ETAS Analysis Workspace

This workspace is organized for low-impact Bosch/ETAS VDP research and handoff. `RoEAIFile.md` remains the authoritative Rules of Engagement document and must be read before any live activity.

## Start Here

1. Read `RoEAIFile.md`.
2. Read `scope/current-scope.md` and `scope/allowed-hosts.txt`.
3. Read `handoff/recon_handoff.md`.
4. Review `findings/findings_draft.md`.
5. Continue only with work allowed by the RoE and current handoff.

## Directory Map

| Path | Purpose |
| --- | --- |
| `RoEAIFile.md` | Authoritative Rules of Engagement. | It can be bypassed if user explict say that him allow.
| `scope/` | Scope confirmation, allowed hosts, and approval-required hosts. |
| `recon/` | Passive recon inventories, domains, docs, apps, and target candidates. |
| `findings/` | Draft findings, confirmed/suspected findings, observations, and false positives. |
| `handoff/` | Current state, notes, request counts, blocked actions, and next steps. |
| `artifacts/` | Local evidence index only; do not store secrets or sensitive data. |
| `scripts/` | Local helper scripts only; no dependency installs without explicit approval. |
| `analysis-template/` | Reusable project template for other VDP or analysis workspaces. |
| `legacy-placeholders/` | Preserved zero-byte placeholder files from the original flat layout. |
| `pentest-agents/` | Existing support material and agent methodology files. |

## Current Safety State

- Confirmed vulnerabilities: none.
- Suspected findings: none.
- External ETAS target requests recorded in the current continuation: 15.
- Latest live validation: inert public search marker check; no reflection and no finding.

Do not submit forms, authenticate, download large/license-gated files, probe APIs, fuzz, brute force, or interact with approval-required hosts unless the RoE and a human approval record allow the exact action.
