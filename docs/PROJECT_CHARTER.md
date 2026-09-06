# CUDA-MM Project Charter

**Status:** Architecture/ownership bootstrap candidate; production implementation not authorized.

## Purpose

CUDA-MM exists to own reusable, provider-neutral **physical memory-management policy** that is genuinely shared across materially different CUDA-JS ecosystem consumers, without turning CUDA-JS into a framework-level memory manager and without moving domain semantics out of their natural owners.

## Owns, when separately accepted

- finite physical memory budgets and pressure classes;
- aligned arena/suballocation planning;
- physical range reuse from owner-supplied non-overlapping logical lifetimes;
- finite pool retention/trimming and fragmentation accounting;
- provider-neutral placement classes and physical-plan identity;
- generic spill/eviction/migration/prefetch strategy;
- generic multi-device physical placement strategy;
- deterministic admission/rejection/explanation for physical plans;
- realization/cleanup orchestration only through public lower contracts.

## Does not own

- native CUDA allocation/free, host registration/mapping, managed-memory, P2P, native pools, prefetch/advice, external-memory, handles/pointers/ABI/provider mechanisms or native lifecycle truth — CUDA-JS owns those;
- Tensor/NN/search/data/media/ray/graph/product resource meaning, logical liveness, aliasing/rematerialization meaning or domain priority — the semantic owner retains those;
- filesystem/source/sink semantics — cuda-io;
- communication/collective/PGAS/RMA semantics — cuda-comm;
- reusable non-memory algorithms merely because they consume or move memory;
- product/model/chess/business/dataset meaning.

## Dependency direction

CUDA-MM may depend on public CUDA-JS for physical realization only after production activation. It may consume normalized constraints from semantic owners through public contracts, but semantic owners must not become required merely to define CUDA-MM core meaning.

CUDA-JS must never depend on CUDA-MM.

## Implementation rule

Maintained CUDA-MM implementation/reference source is JavaScript/TypeScript. Restricted Device-JS is allowed only through public CUDA-JS contracts under a separately accepted profile.

No repository-local C/C++/CUDA/PTX/native FFI/provider binding or copied CUDA ABI/native authority is permitted.

## Activation gate

Issue #3 decides whether production CUDA-MM is justified. Issue #4 must test a domain-neutral constraint/physical-plan model against at least two materially different consumers, unless one exceptionally strong consumer independently satisfies the deletion/reuse tests.

An accepted bounded production specification is required before source/API implementation.

## Deletion/substitution rule

Deleting CUDA-MM leaves CUDA-JS complete and leaves every upper semantic consumer semantically complete. Consumers may revert to explicit public CUDA-JS realization or owner-local planning. Deleting one consumer leaves CUDA-MM coherent.

## Non-goals

Universal allocator, hidden global memory manager, automatic managed-memory policy, universal out-of-core engine, automatic multi-GPU balancing, native provider abstraction, or implementation merely because CUDA exposes memory-management APIs.