# JSALT 2026 — Learned Dynamic Downsampling for Speech LLMs

Static GitHub Pages site for experiment reports and research analysis on learned boundary
policies that compress frozen speech features before a LoRA-adapted Llama decoder.

**▶ Browse the site: https://borrisonxiao.github.io/jsalt26-downsampling/**

## Pages

- [`index.html`](index.html) — project dashboard and navigation.
- [`reports/segmenter-training.html`](reports/segmenter-training.html) — navigable wrapper
  for the cumulative experiment report.
- [`reports/segmenter-training-standalone.html`](reports/segmenter-training-standalone.html)
  — original self-contained report with inline figures.
- [`research/decoder-segmenter-bias.html`](research/decoder-segmenter-bias.html) — literature
  review, hypothesis audit, mathematical framing, and prioritized experiments for lower kept
  ratios.
- [`assets/site.css`](assets/site.css) — shared styling for the dashboard and research pages.

## Adding another page

1. Put experiment reports under `reports/` and analysis pages under `research/`.
2. Link the new page from the card grid in `index.html`.
3. Reuse `assets/site.css` and the existing navigation markup for a consistent layout.

No site generator or JavaScript build is required. GitHub Pages serves the committed HTML and
CSS directly from the `main` branch.
