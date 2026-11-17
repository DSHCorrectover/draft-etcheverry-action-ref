# conformance matrices for draft-etcheverry-action-ref

Three independent implementations, one identifier claim, committed digests. Runnable offline from the checkout.

| Matrix | Claim being checked | Verifier |
|---|---|---|
| `conformance/trail/` | TrailRecord anchoring produces identical `action_ref` under JCS | `verify.mjs` |
| `conformance/agentgraph/` | action_ref v1 vectors + JCS cross-implementation comparison | `verify.mjs` |
| `conformance/agentavow/` | agentavow JCS v1 vectors | `verify.py` |

**For implementers picking up the draft** ([draft-etcheverry-action-ref-00.txt](./draft-etcheverry-action-ref-00.txt)): the fastest way to check your `action_ref` is canonicalization-stable is to point `verify.mjs`/`verify.py` at your own records — expected digests are committed next to the vectors, and disagreement is a bug report, not a failure. The JCS comparison matrices exist because two implementations disagreed on number formatting before they disagreed on anything else; the draft's canonicalization section is load-bearing.

Draft by P. Etcheverry (Rama). Correctover maintains these conformance matrices and the post-execution layer that consumes the identifier ([argentum-core](https://github.com/DSHCorrectover/argentum-core), listed on the official MCP Registry; verdict layer: [correctover-recovery-admission](https://github.com/DSHCorrectover/correctover-recovery-admission)).

*AI-assisted disclosure: maintained with AI assistance, reviewed by Guigui Wang.*
