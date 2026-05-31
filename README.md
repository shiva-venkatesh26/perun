# Perun

Perun is an AMD GPU focused inference engine.

This is a forked project. It starts from an existing production-grade serving runtime and narrows the optimization target around frontier MoE models on AMD Instinct GPUs.

## Direction

Perun is being developed for:

- AMD Instinct first inference performance.
- Frontier MoE serving for Kimi K2.6, MiMo-V2.5-Pro, DeepSeek V4 Pro, and similar architectures.
- ROCm-native optimization across AITER, Triton, TileLang, CK, HIP, RCCL, attention, MoE, quantization, KV cache, and topology-aware scheduling.
- Long-context inference, including 256K to 1M context workloads.
- Upstream-compatible changes where practical, with deliberate divergence only when AMD-focused performance requires it.

## Target Models

The north-star model families are:

- Kimi K2.6
- MiMo-V2.5-Pro
- DeepSeek V4 Pro

These models stress the parts of inference that matter most for AMD datacenter serving: MoE routing, custom attention, MLA or hybrid attention, low-precision weights and KV cache, long contexts, speculative decoding, and distributed execution.

## Development Principles

- Keep rebasing from upstream practical while Perun is still early.
- Benchmark against strong ROCm serving baselines before accepting major runtime or kernel changes.
- Isolate AMD-specific kernels and scheduling experiments behind clean interfaces.
- Prefer correctness and reproducibility before micro-optimization.
- Treat production serving behavior as part of the performance problem.

## Current Status

Perun is currently an early fork. Some commands, package names, and internal module names may still reflect the source project until Perun-specific installation and deployment paths are added.

## Upstream

Perun is forked from [sgl-project/sglang](https://github.com/sgl-project/sglang), licensed under Apache-2.0.
