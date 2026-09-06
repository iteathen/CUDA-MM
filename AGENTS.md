# CUDA-MM Agent Entry Point

Read before changing the repository.

Authority order: owner instruction -> this file -> accepted ADRs -> accepted specs -> project charter -> protected current-state files -> issues/roadmaps/evidence.

Use the governing cycle for every meaningful unit:

`assess -> research -> reassess -> plan -> execute -> qualify -> review -> cleanup/document`

Use `LEGO -> SOLID -> CUPID -> KISS` and preserve one visible owner for every semantic/resource/lifecycle fact.

## Repository role

CUDA-MM is the reserved JavaScript/TypeScript owner for reusable **cross-domain physical memory-management policy** above public CUDA-JS.

When separately accepted from consumer evidence, possible CUDA-MM semantics include finite budgets/pressure, aligned arenas/suballocation, lifetime-driven physical range reuse, finite pooling/fragmentation policy, provider-neutral placement classes, spill/eviction/migration/prefetch strategy, deterministic physical-plan identity, and multi-device physical placement.

Repository creation does not authorize production source/API. Issue #3 is the production activation gate; issue #4 is the first cross-consumer falsifier.

## Hard boundaries

CUDA-JS is the sole native CUDA/provider owner. Native allocation/free, host registration/mapping, managed allocation, peer access/copy, native pools, prefetch/advice calls, external memory, CUDA handles/pointers, ABI structs, provider discovery and native lifecycle/error truth remain in CUDA-JS.

Semantic consumers retain **logical meaning and liveness**. Tensor knows Tensor lifetimes/aliasing; CUDA-MCGS knows search/evaluator resource epochs; cuda-data knows column/table lifetimes; other domains retain their own meaning. CUDA-MM may consume normalized generic constraints but must not learn domain vocabulary.

Maintained CUDA-MM source/reference code is JavaScript/TypeScript. Restricted Device-JS is permitted only through public CUDA-JS contracts if an accepted CUDA-MM profile genuinely requires device-side generic memory-management behavior.

No Python, C/C++, CUDA C++, hand PTX, direct native FFI, native addons, CUDA header/ABI ownership, provider bindings, raw pointers/handles, private lower imports or consumer-local native workarounds.

A missing native mechanism is a CUDA-JS gap. A missing domain semantic stays with that domain. A reusable non-memory algorithm requires its own natural JS/TS owner.

## Deletion tests

CUDA-JS must remain complete and usable if CUDA-MM is deleted. Upper semantic consumers must remain semantically complete if CUDA-MM is deleted; they may lose only an optional shared physical-policy realization. Deleting any one consumer must leave the CUDA-MM contract coherent.

## Current control state

Issue #1 owns bootstrap/architecture integration. Issue #2 owns repository-control alignment; do not claim protected-main parity until live readback proves it. Issue #3/#4 are assessment authority only, not implementation specifications.