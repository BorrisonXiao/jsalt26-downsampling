# JSALT 2026 — Learned Dynamic Downsampling for Speech LLMs

Cumulative experiment report for a learned boundary policy that compresses frozen speech
features before a LoRA-adapted Llama decoder. The current report compares wav2vec2 and
WavLM, fixed/native/alignment controls, Bernoulli and label-dependent policies, and
decoder/segmenter initialization studies on LibriSpeech-100h.

**▶ View the report: https://borrisonxiao.github.io/jsalt26-downsampling/**

The self-contained `index.html` is organized by research question:

0. **Summary** — what was compared, the WER for each system, and what it tells us.
1. **WavLM results** — learned policies, fixed pooling, no downsampling, and char- and
   phone-aligned controls.
2. **What causes the WER gap?** — a setup table, WER plots, decoder initialization,
   segmenter input, and a same-decoder oracle/cold/post-RL boundary comparison.
3. **wav2vec2 and WavLM** — the same learned-policy experiments with both encoders.
4. **Previous boundary history** — Bernoulli versus first-order autoregressive policies,
   including the live long-horizon three-seed study.
5. **Method** — data, architecture, pooling semantics, and training curriculum.
6. **Failure audit** — the original collapse and its two distinct mechanisms.
7. **Reward/multi-task ablations** — three-seed NLL/CER and frozen/co-trained decoder results.
8. **Qualitative boundaries** — verified char-CTC intervals versus learned boundaries.
9. **wav2vec2 WER versus compression** — the historical plot and exact table.
10. **Appendix** — architecture and trainable-parameter counts.

Open `index.html` directly, or use the hosted link above.
