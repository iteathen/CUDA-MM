# CUDA-MM

CUDA-MM is the reserved JavaScript/TypeScript owner for reusable, cross-domain **physical memory-management policy** in the CUDA-JS ecosystem.

CUDA-JS remains the sole native CUDA/provider boundary. Semantic consumers such as CUDA-JS-Tensor, CUDA-MCGS, cuda-data, cuda-io and products retain the meaning and logical lifetime of their resources. CUDA-MM may become the shared owner for domain-neutral allocation planning, suballocation, lifetime-based physical reuse, pooling, pressure, placement and related policy only after consumer evidence justifies a production layer.

## Boundary

```text
Tensor / MCGS / Data / other semantic owners
    logical meaning + owner-computed lifetime constraints
                         ↓
                      CUDA-MM
    optional reusable physical memory-management policy
                         ↓
                      CUDA-JS
       sole native CUDA/provider mechanism boundary
                         ↓
                        CUDA
```

CUDA-MM does not own native allocation/registration/managed-memory/P2P/prefetch/advice/pool/external-memory mechanisms, and it does not own Tensor/search/data/model/etc. liveness semantics.

Maintained CUDA-MM implementation/reference code is JavaScript/TypeScript. Restricted Device-JS is allowed only through public CUDA-JS contracts under a separately accepted profile. No C/C++/CUDA/PTX/native FFI/provider implementation belongs here.

## Current status

Architecture bootstrap only. **No production CUDA-MM source/API is authorized.**

- [Project charter](docs/PROJECT_CHARTER.md)
- [Architecture decisions](docs/decisions/README.md)
- [Specifications](docs/specs/README.md)
- [Current status](STATUS.md)
- [Current execution seam](next_step.yaml)

Tracking:

- #1 — architecture/bootstrap integration;
- #2 — repository-control alignment;
- #3 — production activation gate;
- #4 — first cross-consumer physical-plan falsifier.

Repository creation and provider availability are not evidence that a production memory manager is needed.