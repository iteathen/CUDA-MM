# Evidence status

This repository follows the shared [iteathen evidence and validation policy](https://github.com/iteathen/.github/blob/main/EVIDENCE_POLICY.md).

## Current posture

CUDA-MM is currently architecture bootstrap only. Its intended boundary is documented, but no production CUDA-MM source/API is authorized.

## Registered claims

| Claim | Evidence class | Status |
| --- | --- | --- |
| `CUDA-MM-PLAN-001` — intended scope: optional reusable cross-domain physical memory-management policy above CUDA-JS | **UNVALIDATED** | planning hypothesis / activation-gated boundary |

The claim record is machine-readable in [`evidence/claims.json`](evidence/claims.json).

## What current evidence establishes

The repository establishes the intended ownership boundary between semantic consumers, optional physical memory-management policy, and CUDA-JS as the native provider boundary.

## What it does not establish

It does not establish that a production memory manager is needed, that the proposed abstraction improves memory use or performance, or that any native/provider behavior is qualified.

## Path to stronger evidence

Activation should require the repository's planned cross-consumer falsifier: materially different consumers must demonstrate a reusable physical-policy need. Any later performance claim requires measured enclosing-system evidence rather than local allocator microbenchmarks alone.

## Non-mutation rule

Evidence work may inspect, test, benchmark, and document CUDA-MM. It must not create or change production memory-management behavior merely to make an evidence claim pass.
