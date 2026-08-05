# JSALT 2026 — Learned Dynamic Downsampling for Speech LLMs

Training-dynamics report for the RL speech-segmenter pilot: a per-frame **boundary policy**
over frozen wav2vec2, trained with **GRPO** to dynamically downsample the audio-token
sequence fed to a LoRA-Llama decoder.

**▶ View the report: https://borrisonxiao.github.io/jsalt26-downsampling/**

The report (`index.html`, self-contained — inline SVG charts + base64 spectrograms, light/dark)
covers:

0. **Background** — the task/data/model/pipeline setup and the cold-start → warmup → joint-RL
   curriculum, for readers who want the full picture before the results.

1. **The collapse and the fix** — how a per-frame entropy bonus + teacher-forced-NLL reward
   drove the boundaries to a degenerate solution, and the fix (drop entropy, longer decoder
   warmup), plus a "revisiting the failure" post-mortem: the collapse history is actually two
   distinct mechanisms (a true GRPO absorbing state, and a separate entropy-driven
   argmax-vs-expected divergence), evidenced from the raw logs and an instrumented GRPO trace.
2. **Training dynamics and reward / multi-task ablations** — the corrected three-seed,
   exact-shared-warm-up NLL replication with mean ± SD, followed by the historical first-pass
   CNN curves and CER-reward context.
3. **Learned boundaries** — predicted boundaries vs char-CTC ground truth, as three rows sharing
   one time axis (spectrogram, gold char alignment, learned boundaries) so they can be traced
   straight down and compared.
4. **Fixed-rate baselines** — the test-clean/test-other WER-vs-compression frontier, with the
   corrected NLL three-seed means and SD error bars plotted at their learned compression rates.
5. **Appendix** — exact architecture and trainable-parameter counts for both segmenter backbones
   (CNN vs Transformer) and the decoder (proj + LoRA-adapted Llama-3.2-1B-Instruct).

Open `index.html` directly, or use the hosted link above.
