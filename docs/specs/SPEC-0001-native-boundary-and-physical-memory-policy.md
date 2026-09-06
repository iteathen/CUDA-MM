# SPEC-0001: Native Boundary and Cross-Domain Physical Memory Policy

**Status:** Architecture/ownership authority candidate; production CUDA-MM profiles remain separately gated.

**Version:** 1.0.0

**Owner:** CUDA-MM

**Lower authority:** `iteathen/CUDA-JS` SPEC-0032

## Purpose

Define the exact ownership boundary between native CUDA memory mechanisms, reusable cross-domain physical memory-management policy, and consumer-owned logical resource semantics.

CUDA-JS remains the sole native CUDA/provider integration owner. CUDA-MM is reserved for provider-neutral physical memory-management policy that can be expressed without domain vocabulary and is independently justified across consumers.

## Repository implementation rule

Maintained CUDA-MM implementation/reference source is JavaScript/TypeScript. Restricted Device-JS generation is permitted only through public CUDA-JS contracts under a separately accepted CUDA-MM profile.

CUDA-MM does not maintain Python, C, C++, CUDA C++, PTX, direct native FFI, native addons, CUDA headers/ABI structs, provider bindings, native handles/pointers, platform discovery code or private lower imports.

A missing native mechanism routes to CUDA-JS before any local workaround.

## CUDA-JS owns

CUDA-JS owns the JS-safe projection, lifecycle and evidence for native memory capabilities, including when separately accepted:

- device allocation/free and bounded views;
- pinned host allocation and host-memory registration/mapping;
- managed allocation;
- peer-access and peer-copy mechanisms;
- native memory-pool resources and operations;
- native prefetch/advice calls;
- external-memory/semaphore interoperability mechanisms;
- native alignment/device/capability facts;
- context/device affinity, leases, deferred failures, cleanup and restart/orphan truth;
- native provider/platform/ABI compatibility evidence.

The existence of one of these mechanisms does not authorize CUDA-MM policy that selects or orchestrates it.

## Semantic consumers own

Each semantic owner retains why a resource exists and its logical constraints. Examples include:

- CUDA-JS-Tensor — Tensor material identity, dtype/shape/layout/aliasing, logical liveness, workspace and Tensor-plan meaning;
- CUDA-MCGS — search/evaluator/resource identity, epochs/freshness, capacities and search-lifecycle meaning;
- cuda-data — column/table/schema/liveness/chunk/out-of-core meaning;
- cuda-io — source/sink/chunking/backpressure meaning;
- other semantic repositories/products — their own resource meaning and domain priority.

A consumer may project normalized generic constraints to CUDA-MM, but CUDA-MM must not infer or recreate the consumer's semantic liveness.

## CUDA-MM may own, when production-activated

Only reusable physical policy that remains coherent across domains, such as:

- finite physical memory budgets and pressure classes;
- byte/alignment/access compatibility for planning;
- aligned arena/suballocation plans;
- physical range reuse from owner-supplied non-overlapping lifetime constraints;
- finite pool retention/trimming strategy;
- fragmentation accounting and bounded compaction strategy where the selected lower mechanisms permit it;
- provider-neutral placement classes;
- physical placement/spill/eviction/migration/prefetch strategy;
- multi-device physical placement strategy;
- deterministic physical-plan identity, provenance and explainable admission/rejection;
- realization/cleanup composition through public CUDA-JS only.

## Generic constraint boundary

A future production contract may consume domain-neutral facts such as:

- opaque consumer resource identity;
- finite bytes and alignment;
- owner-supplied logical lifetime interval/epoch constraints;
- read/write/access compatibility;
- aliasability/reuse restrictions;
- persistence class;
- movability/rematerialization permission only when explicitly supplied by the semantic owner;
- allowed physical placement classes;
- device affinity/set constraints;
- finite budget/pressure class.

The contract fails the ownership test if CUDA-MM needs fields such as Tensor node, activation, gradient, search node, evaluator slot, Arrow column, frame, acceleration structure, model/checkpoint or other domain vocabulary.

## Activation and deletion tests

This specification does not authorize production source/API.

Production activation requires issue #3 to conclude that reusable policy is justified using #4 or equivalent evidence. The first production semantic/profile contract must then be accepted separately.

Any accepted CUDA-MM design must preserve:

1. CUDA-JS remains coherent and complete if CUDA-MM is deleted.
2. Every semantic consumer remains semantically complete if CUDA-MM is deleted; only optional shared physical policy is lost.
3. Deleting any one consumer leaves CUDA-MM coherent.
4. No native CUDA/provider authority moves upward.
5. No consumer logical liveness/meaning moves downward.

## Existing CUDA-JS memory issues

CUDA-JS issues for native caller-owned pinned/registered host memory, managed memory and peer access/copy remain CUDA-JS-owned. CUDA-MM may later select those capabilities through public contracts, but repository creation does not transfer or duplicate them.

## Non-goals

No global allocator singleton, no transparent unified-memory fallback, no universal oversubscription guarantee, no hidden host spill, no universal multi-GPU balancing, no domain-specific planner, no reusable non-memory algorithm library, and no support/performance claim from architecture acceptance alone.