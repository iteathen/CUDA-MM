# Repository context: CUDA-MM

Universal engineering and design guidance comes from the account-global `AGENTS.md`.

## Mission and ownership

CUDA-MM is the reserved JavaScript/TypeScript owner for reusable cross-domain physical memory-management policy above public CUDA-JS when consumer evidence justifies it: budgets/pressure, arenas/suballocation, physical range reuse, pooling/fragmentation, provider-neutral placement classes, spill/eviction/migration/prefetch strategy, deterministic physical-plan identity, and multi-device physical placement.

CUDA-JS remains the native CUDA/provider owner. Semantic consumers retain logical meaning and liveness; CUDA-MM consumes only normalized generic constraints.

## Local routing

Accepted repository ADR/specification files and current issues own activation and implementation authority.

## Local constraints

Maintained source is JavaScript/TypeScript. No Python, direct native FFI/CUDA implementation, raw pointers/handles, provider bindings, private lower imports, or consumer-specific semantic ownership.