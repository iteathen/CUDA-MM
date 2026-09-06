# CUDA-MM architecture decisions

This directory records accepted architectural decisions. Later decisions may supersede earlier ones; retained records explain that history.

- [ADR-0001: Independent cross-domain physical memory-policy owner](ADR-0001-independent-physical-memory-policy-owner.md) — establishes CUDA-MM above CUDA-JS native mechanisms and below/alongside semantic consumers without moving logical liveness.

See the [specification index](../specs/README.md) before implementing any capability.