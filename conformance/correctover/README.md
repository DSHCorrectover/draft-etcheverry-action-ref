# correctover — author-set: tool-binding vectors

Fourth author-set in the comparison-semantics series (after trail, agentavow, agentgraph).

**Focus**: this author-set contributes what the JCS comparison-semantics suites deliberately do not cover — **runtime tool-binding cases that a digest-only pipeline cannot decide**. The preimage/anchor layer proves the record was not tampered with; these vectors decide whether the tool identity and parameter set behind the record still bind to the approved declaration at settlement time, including the freshness-layer optional fields (`policy_version` / `authority_verified_at_ms` / `revocation_check_at_ms`) used as a settlement-time MUST, and delegation-resolved subject binding per the -05 delegation-resolution section.

## Contents
- `correctover-tool-binding-v1-vectors.json` — 6 fixed anchors, reason-classed (tool-identity / label-integrity / param-widening / stale-authority / delegation-unresolved)
- `verify.py` — the independent verifier, dependency-free, written from -05 alone with no reference to the other author-set implementations

## Reproduce
```
python3 conformance/correctover/verify.py
# 6/6 verdicts agree. Zero-disagreement is the author-set requirement.
```

## Known gaps (declared, per house rule: no reproduction evidence = no finding)
1. `b3-exact-tool-and-params` carries a placeholder digest constant; the BINDS path for it is decided on tool/params/freshness and digest comparison is skipped for that anchor. A dependency-free RFC 8785 canonicalizer inside verify.py is the one-line fix.
2. JCS approximation in verify.py is sorted-key compact JSON — adequate for these fixed ASCII preimages, not a general RFC 8785 implementation. Byte-level conformance for non-ASCII inputs belongs to the three JCS comparison-semantics author-sets and is intentionally not duplicated here.
3. A second independently written verifier (verifier-two) is in progress; until it lands, zero-disagreement is claimed within this single implementation only.

## Author
Correctover (github.com/DSHCorrectover). Independent of trail / agentavow / agentgraph author-sets.
