# JSALT 2026 — Learned Dynamic Downsampling for Speech LLMs

Training-dynamics report for the RL speech-segmenter pilot: a per-frame **boundary policy**
over frozen wav2vec2, trained with **GRPO** to dynamically downsample the audio-token
sequence fed to a LoRA-Llama decoder.

**▶ View the report: https://borrisonxiao.github.io/jsalt26-downsampling/**

The report (`index.html`, self-contained — inline SVG charts + base64 spectrograms, light/dark)
covers:

1. **The collapse and the fix** — how a per-frame entropy bonus + teacher-forced-NLL reward
   drove the boundaries to a degenerate solution, and the fix (drop entropy, longer decoder
   warmup), plus a "revisiting the failure" post-mortem: the collapse history is actually two
   distinct mechanisms (a true GRPO absorbing state, and a separate entropy-driven
   argmax-vs-expected divergence), evidenced from the raw logs and an instrumented GRPO trace.
2. **Training dynamics** — reward / multi-task ablations (NLL vs free-running CER reward;
   frozen vs co-trained decoder), all CNN-backbone.
3. **Learned boundaries** — predicted boundaries vs char-CTC ground truth, as three rows sharing
   one time axis (spectrogram, gold char alignment, learned boundaries) so they can be traced
   straight down and compared.
4. **Fixed-rate baselines** — the WER-vs-compression frontier the learned segmenter must beat,
   with our current trained models (CNN backbone, labeled) plotted on it.
5. **Appendix** — exact architecture and trainable-parameter counts for both segmenter backbones
   (CNN vs Transformer) and the decoder (proj + LoRA-adapted Llama-3.2-1B-Instruct).

Open `index.html` directly, or use the hosted link above.
