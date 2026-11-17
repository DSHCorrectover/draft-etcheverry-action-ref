# draft-etcheverry-action-ref — conformance matrices for the `action_ref` Internet-Draft

Public conformance vectors and independent verification for [draft-etcheverry-action-ref-00](./draft-etcheverry-action-ref-00.txt) ("Action Reference: A Deterministic Identifier for Agent Actions", individual submission, June 2026).

Our position: a deterministic correlation identifier for agent actions is the substrate every downstream verdict needs — who did what, to which target, under which grant. This repo makes the draft's identifier claim **checkable across independent implementations** rather than asserted.

## Conformance matrices

| Matrix | What it proves | Verifier |
|---|---|---|
| `conformance/trail/` | JCS comparison vectors for TrailRecord anchoring | `verify.mjs` |
| `conformance/agentgraph/` | action_ref v1 vectors + JCS cross-check | `verify.mjs` |
| `conformance/agentavow/` | agentavow JCS v1 vectors | `verify.py` |

Every matrix is runnable from the checkout with no network access; expected digests are committed alongside the vectors.

## Related Correctover work

- Post-execution accountability: [argentum-core](https://github.com/DSHCorrectover/argentum-core) (listed on the official MCP Registry)
- Pre-execution verdict layer: [correctover-recovery-admission](https://github.com/DSHCorrectover/correctover-recovery-admission)

---

**Commercial verification engagements** — post-migration authorization integrity assessment, court-ready dossier: [tiers & free sample](https://dshcorrectover.github.io/correctover-recovery-admission/services.html) · wangguigui@correctover.com

*AI-assisted disclosure: this repository is maintained with AI assistance, reviewed by Guigui Wang.*
