# CUDA-MM Status

**Updated:** 2026-09-06

## Current state

CUDA-MM is being bootstrapped as the reserved JavaScript/TypeScript owner for reusable cross-domain physical memory-management policy above public CUDA-JS.

No production allocator/planner source, package, public API, provider integration, native qualification, performance claim or support claim is authorized.

## Ownership

- CUDA-JS owns all maintained native CUDA/provider memory mechanisms and native lifecycle/error truth.
- Semantic consumers own logical resource meaning and liveness.
- CUDA-MM may own only domain-neutral physical memory policy that survives the deletion tests and is independently activated.
- Maintained CUDA-MM source/reference code is JavaScript/TypeScript plus only separately accepted restricted Device-JS through public CUDA-JS.

## Current issues

- #1 — architecture/bootstrap integration.
- #2 — repository-control alignment. Live readback after repository bootstrap shows `main` exists but is **not protected**; do not claim CUDA-family governance parity yet.
- #3 — production activation gate. No production source/API before it resolves positively and a bounded production spec is accepted.
- #4 — first cross-consumer constraint/physical-plan falsifier using Tensor plus at least one materially different consumer.

## Current executable seam

Complete #1 architecture integration without implementing memory-management code. Then execute #4 as research/assessment feeding #3. Repository-control work under #2 is independent and must use live GitHub readback rather than desired-state prose.

## Explicit non-claims

- no production CUDA-MM capability exists;
- no existing CUDA-JS native memory issue has moved here;
- no Tensor/MCGS/data logical liveness has moved here;
- no generic arena/pool/placement/spill policy has yet been accepted as a production CUDA-MM contract;
- no native CUDA/provider/platform support is claimed;
- no performance benefit is claimed.