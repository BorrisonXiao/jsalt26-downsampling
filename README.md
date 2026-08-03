# JSALT 2026 — Learned Dynamic Downsampling for Speech LLMs

Training-dynamics report for the RL speech-segmenter pilot: a per-frame **boundary policy**
over frozen wav2vec2, trained with **GRPO** to dynamically downsample the audio-token
sequence fed to a LoRA-Llama decoder.

**▶ View the report: https://borrisonxiao.github.io/jsalt26-downsampling/**

The report (`index.html`, self-contained — inline SVG charts + base64 spectrograms, light/dark)
covers:

1. **The collapse and the fix** — how a per-frame entropy bonus + teacher-forced-NLL reward
   drove the boundaries to a degenerate solution, and the fix (drop entropy, longer decoder
   warmup).
2. **Training dynamics** — reward / multi-task ablations (NLL vs free-running CER reward;
   frozen vs co-trained decoder).
3. **Learned boundaries** — predicted boundaries vs char-CTC ground truth over log-mel
   spectrograms.
4. **Fixed-rate baselines** — the WER-vs-compression frontier the learned segmenter must beat.

Open `index.html` directly, or use the hosted link above.
