# ADR-0001: Independent Cross-Domain Physical Memory-Policy Owner

**Status:** Candidate for bootstrap acceptance
**Date:** 2026-09-06

## Context

The CUDA-JS ecosystem now has a hard native boundary: CUDA-JS is the only repository that may own maintained native CUDA/provider integration. At the same time, multiple semantic systems can plausibly need reusable physical memory planning beyond direct allocation primitives: Tensor has material/lifetime planning; CUDA-MCGS has finite device-resident resource capacities/epochs; data/I/O systems may later need placement, reuse and pressure policy.

Putting cross-domain physical policy into CUDA-JS would make the native boundary increasingly framework-like. Putting generic policy into the first semantic consumer would give one domain ownership over unrelated workloads. But repository creation alone does not prove that a new shared production layer is needed.

## Decision

`CUDA-MM` is the reserved JavaScript/TypeScript owner for reusable provider-neutral **physical memory-management policy** that survives consumer deletion and can be expressed without domain vocabulary.

CUDA-JS retains all native allocation/registration/managed/P2P/prefetch/advice/pool/external-memory/provider mechanisms and native lifecycle/error truth.

Semantic consumers retain logical resource meaning and liveness. They may project generic constraints to CUDA-MM only after a separately accepted CUDA-MM production profile exists.

CUDA-MM starts dormant: issue #3 must explicitly activate or park production based on issue #4's cross-consumer falsifier or equivalent evidence.

## Deletion tests

- Delete CUDA-MM: CUDA-JS remains complete; upper consumers remain semantically complete and may use explicit CUDA-JS realization/owner-local planning.
- Delete any one consumer: CUDA-MM's generic contract remains coherent.
- Delete CUDA-JS: CUDA-MM loses its CUDA realization but retains provider-neutral physical-policy semantics; it does not recreate native CUDA access.

## Consequences

The ecosystem has a named home for future generic memory policy without forcing that policy into the native core or a domain library. Native mechanisms remain centralized. Logical liveness remains decentralized with semantic owners. Production CUDA-MM implementation remains evidence-gated rather than assumed.