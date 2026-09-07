# CUDA-MM Agent Entry Point

Read before changing the repository.

Authority order: owner instruction -> this file -> accepted ADRs -> accepted specs -> project charter -> protected current-state files -> issues/roadmaps/evidence.

Use the governing cycle for every meaningful unit:

`assess -> research -> reassess -> plan -> execute -> qualify -> review -> cleanup/document`

Use `LEGO -> SOLID -> CUPID -> KISS` and preserve one visible owner for every semantic/resource/lifecycle fact.

LEGO is the outer architecture rule: ownership, universality, replaceability, scope containment, damage-limiting encapsulation, supported connection surfaces, and context containment. **The application/system is the outermost LEGO.** Its supported external inputs, outputs, commands, events, data contracts, and lifecycle entry/exit points are its public **studs/surfaces**. Large sections, subsystems, components, and large objects should preferentially compose smaller child LEGOs when that preserves cohesion; the parent owns the external responsibility and hides child topology.

A LEGO is too large when one agent cannot hold its complete authoritative working set—contract/studs/surfaces, implementation, invariants, lifecycle/resource/failure rules, tests/conformance, and immediate dependency/consumer interfaces—in focused attention with substantial headroom for reasoning and review. Context fit is a first-class boundary criterion alongside semantic, lifecycle, resource/failure, substitution, and change cohesion. When exceeded, recursively split at the strongest real seam or narrow scope; do not create arbitrary modules that duplicate truth or require cross-boundary internal knowledge. Callers connect through deliberate studs/surfaces and never drill through a parent to a private child. Inside a valid LEGO, SOLID structures responsibilities and dependency direction, CUPID shapes the implementation, and KISS removes remaining unjustified complexity; lower levels may not defeat higher ones.

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

## Execution efficiency / mutation hygiene

These are **default suggestions, not mandatory sequencing rules**. Use them when they reduce uncertainty, duplication, or avoidable mutation risk. Current validated information and repository-specific authority can justify a different sequence; do not perform a step merely for procedural completeness.

- **Read before write when the read can materially improve the decision.** Reuse prior validated context when its assumptions still hold. A safe, isolated, informative write can itself be research.
- **Prefer one ownership unit at a time when that keeps reasoning and review clear.** Cross ownership boundaries deliberately when the real problem or solution spans them.
- **Introduce new mechanisms when they solve a real problem.** Avoid gratuitous machinery, not invention.
- **When state is unexpected, stop and assess before acting.** Then choose whether to preserve it, repair forward, or roll back; rollback is not the default.
- **Qualify proportionally.** Validate before propagation when remaining uncertainty would become meaningfully more expensive. For simple, well-understood, mechanical changes, propagate then qualify once when that is cheaper and equally sound.
- **Reuse valid evidence and established conclusions.** Do not repeat research or validation solely to satisfy process form.
- Prefer the path that uses available information to reduce uncertainty and rework at reasonable cost while preserving correctness, ownership, recoverability, and honest evidence.
