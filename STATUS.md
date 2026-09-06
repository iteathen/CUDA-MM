# CUDA-MM Status

**Updated:** 2026-09-06

## Current state

CUDA-MM architecture/ownership bootstrap is **complete**. CUDA-MM is the accepted reserved JavaScript/TypeScript owner for reusable cross-domain physical memory-management policy above public CUDA-JS.

No production allocator/planner source, package, public API, provider integration, native qualification, performance claim or support claim is authorized.

## Integrated ownership boundary

- CUDA-MM SPEC-0001 and ADR-0001 establish the reserved cross-domain physical-policy owner and deletion tests.
- CUDA-JS SPEC-0033 recognizes CUDA-MM while retaining every native CUDA/provider memory mechanism and native lifecycle/evidence fact in CUDA-JS.
- CUDA-JS-Tensor SPEC-0013 keeps Tensor semantic liveness/material planning in Tensor and permits only future optional domain-neutral projection after CUDA-MM activation.
- CUDA-MCGS SPEC-0016 keeps search/evaluator/resource pressure/reclamation/lifecycle meaning in MCGS and permits only future optional domain-neutral projection after CUDA-MM activation.
- cuda-data, cuda-io, cuda-media and cuda-ray current-state authorities name CUDA-MM as the reserved optional physical-policy owner without making it a production dependency.
- UCI-Arena-Vector routes reusable cross-domain physical memory policy to CUDA-MM while retaining product/resource meaning and its existing numerical/search critical paths.

Existing CUDA-JS native memory issues remain where they are: caller-owned pinned/registered host memory, managed memory and peer access/copy are CUDA-JS mechanisms. CUDA-MM may later select those mechanisms through public contracts only if production is separately activated.

## Ownership

- CUDA-JS owns all maintained native CUDA/provider memory mechanisms and native lifecycle/error truth.
- Semantic consumers own logical resource meaning and liveness.
- CUDA-MM may own only domain-neutral physical memory policy that survives the deletion tests and is independently activated.
- Maintained CUDA-MM source/reference code is JavaScript/TypeScript plus only separately accepted restricted Device-JS through public CUDA-JS.

## Current issues

- #1 — architecture/bootstrap integration: **completed**.
- #2 — repository-control alignment: **open**. Live GitHub readback still reports `main` **not protected**; do not claim CUDA-family governance parity until that is actually corrected and read back.
- #4 — **current executable assessment**: test one domain-neutral memory constraint/physical-plan model against Tensor and at least one materially different consumer.
- #3 — production activation gate: consume #4's evidence and explicitly activate or park production CUDA-MM.

## Current executable seam

Execute #4 as assessment/research only. Compare current owner-local planning in CUDA-JS-Tensor and CUDA-MCGS, project only domain-neutral constraints, and falsify the abstraction if CUDA-MM needs consumer vocabulary. Feed the result into #3.

If #3 activates production, accept the smallest bounded semantic/profile specification **before** source/API work. If #3 rejects/defer, keep CUDA-MM as a dormant reserved owner.

Repository-control work under #2 is independent and must use live GitHub readback rather than desired-state prose.

## Explicit non-claims

- no production CUDA-MM capability exists;
- no existing CUDA-JS native memory issue has moved here;
- no Tensor/MCGS/data/media/ray logical liveness has moved here;
- no generic arena/pool/placement/spill policy has yet been accepted as a production CUDA-MM contract;
- no automatic managed-memory, spill, migration or multi-GPU placement behavior exists;
- no native CUDA/provider/platform support is claimed;
- no performance benefit is claimed.
