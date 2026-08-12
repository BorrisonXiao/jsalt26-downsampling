# JSALT 2026 — Learned Dynamic Downsampling for Speech LLMs

Static GitHub Pages site for experiment reports, analyses, and proposals on learned boundary
policies that compress frozen speech features before a LoRA-adapted Llama decoder.

**▶ Browse the site: https://borrisonxiao.github.io/jsalt26-downsampling/**

## Pages

- [`index.html`](index.html) — project dashboard and navigation.
- [`reports/segmenter-training.html`](reports/segmenter-training.html) — navigable wrapper
  for the cumulative experiment report.
- [`reports/segmenter-training-standalone.html`](reports/segmenter-training-standalone.html)
  — original self-contained report with inline figures.
- [`research/index.html`](research/index.html) — collection page for research analyses.
- [`research/decoder-segmenter-bias.html`](research/decoder-segmenter-bias.html) — literature
  review, hypothesis audit, mathematical framing, and prioritized experiments for lower kept
  ratios.
- [`proposals/index.html`](proposals/index.html) — collection page for experiment proposals.
- [`proposals/on-policy-prefix-distillation.html`](proposals/on-policy-prefix-distillation.html)
  — navigable OPD proposal wrapper.
- [`proposals/on-policy-prefix-distillation-standalone.html`](proposals/on-policy-prefix-distillation-standalone.html)
  — self-contained OPD proposal.
- [`assets/site.css`](assets/site.css) — shared styling for the dashboard and research pages.

## Adding another page

1. Put experiment reports under `reports/`, analyses under `research/`, and proposals under `proposals/`.
2. Link the new item from its collection page. Link the collection from `index.html` only when adding a new collection.
3. Reuse `assets/site.css` and the existing navigation markup for a consistent layout.

No site generator or JavaScript build is required. GitHub Pages serves the committed HTML and
CSS directly from the `main` branch.
