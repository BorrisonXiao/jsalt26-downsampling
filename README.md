# JSALT 2026 — Learned Dynamic Downsampling for Speech LLMs

Cumulative experiment report for a learned boundary policy that compresses frozen speech
features before a LoRA-adapted Llama decoder. The current report compares wav2vec2 and
WavLM, fixed/native/alignment controls, Bernoulli and label-dependent policies, and
decoder/segmenter initialization studies on LibriSpeech-100h.

**▶ View the report: https://borrisonxiao.github.io/jsalt26-downsampling/**

The self-contained `index.html` is organized by research question:

0. **Evidence map** — current claims, controlled comparisons, and evidence status.
1. **WavLM benchmark matrix** — learned policies and fixed, native-rate, char-, and
   phone-aligned quality–compression controls.
2. **Controlled attribution** — detector features, decoder initialization, and a
   same-decoder oracle/cold/post-RL boundary swap.
3. **Encoder replication** — matched wav2vec2 versus WavLM results.
4. **Label-dependent sampling** — Bernoulli versus first-order autoregressive policies,
   including the live long-horizon three-seed study.
5. **Method** — data, architecture, pooling semantics, and training curriculum.
6. **Failure audit** — the original collapse and its two distinct mechanisms.
7. **Reward/multi-task ablations** — three-seed NLL/CER and frozen/co-trained decoder results.
8. **Qualitative boundaries** — verified char-CTC intervals versus learned boundaries.
9. **wav2vec2 frontier** — the historical WER–compression plot and exact table.
10. **Appendix** — architecture and trainable-parameter counts.

Open `index.html` directly, or use the hosted link above.
