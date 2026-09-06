# CUDA-MM specifications

**Architecture/ownership authority is accepted; no production memory-management capability specification is accepted yet.**

- [`SPEC-0001-native-boundary-and-physical-memory-policy.md`](SPEC-0001-native-boundary-and-physical-memory-policy.md) — accepted cross-cutting ownership rule: CUDA-JS remains the sole native CUDA/provider boundary, semantic consumers retain logical resource meaning/liveness, and CUDA-MM is reserved for reusable cross-domain physical memory-management policy. This specification does not authorize a production allocator/planner API.

Issue #3 is the production activation gate. Issue #4 is the first consumer-assessment falsifier. Production implementation requires a separately accepted bounded semantic/profile specification after those gates justify the layer.

Start with the [project charter](../PROJECT_CHARTER.md) and [architecture decision](../decisions/README.md).
