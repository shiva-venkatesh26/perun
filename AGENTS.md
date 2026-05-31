# Perun

Perun is an AMD GPU focused inference engine forked from SGLang.

Primary direction:
- Optimize serving for frontier MoE models on AMD Instinct GPUs.
- Treat Kimi K2.6, MiMo-V2.5-Pro, and DeepSeek V4 Pro as north-star model families.
- Prefer ROCm-native performance work around AITER, Triton, TileLang, CK, HIP, RCCL, attention, MoE, quantization, KV cache, and topology-aware scheduling.
- Keep changes scoped and upstream-compatible where practical.

Development notes:
- Preserve SGLang compatibility unless a Perun-specific divergence is intentional.
- Benchmark against upstream SGLang and vLLM ROCm before accepting major runtime or kernel changes.
- Avoid broad refactors that make rebasing from upstream difficult.
