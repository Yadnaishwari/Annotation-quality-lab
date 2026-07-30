# Annotation Quality Lab
**Live tool:** [Try it here](https://yadnaishwari.github.io/Annotation-quality-lab/annotation-quality-lab.html)


A small, hands-on study in human-data operations: designing a labeling task, running it, and measuring whether the labels can be trusted. Models are only as good as the data they learn from — and that data is only as good as the process that produces it.

## What this is

A self-contained tool for running a labeling task against a rubric and measuring label quality:
- **Cohen's κ** (inter-annotator agreement, corrected for chance)
- **Accuracy vs. a gold set** (are labelers *right*, not just consistent?)
- **Label distribution** and a **disagreement queue** for adjudication

The task: rate an AI assistant's response on a 1–3 scale (Poor / Adequate / Excellent), given a rubric with a deliberate tie-breaking rule and a hard "factual errors = 1" rule.

## Why it matters

Response-quality rating is the backbone of preference and evaluation data for language models. This project mirrors — in miniature — the human-data operations behind that work: labeling interfaces, quality standards, and operational visibility (κ, per-labeler accuracy, an adjudication queue).

## How to run it

1. Open the [live tool](https://yadnaishwari.github.io/Annotation-quality-lab/annotation-quality-lab.html) in a browser.
2. Label all 20 items as **Labeler A**.
3. Get a second person to label the same items as **Labeler B** (or label again yourself on a different day, noting that this measures intra-rater consistency, not true inter-annotator agreement).
4. Read the live metrics panel; **export results** to save your run.

## Results from my run

- Items: 20 · Gold items: 10 · Labelers: A, B
- Cohen's κ: 0.27 (band: fair), over 20 co-labeled items; raw agreement 55%
- Accuracy vs gold: A 50% (5/10) · B 40% (4/10)
- Label distribution: 1 → 8, 2 → 20, 3 → 12
- Disagreements: 9 of 20 co-labeled items

## What the disagreements taught me

Two disagreements stood out. On IT-10 ("why is the sky blue," answered with a
factually wrong response), Labeler A rated it a 3 — missing the factual error
entirely — while Labeler B correctly caught it at 1. On IT-15 (a seasons
misconception), the roles flipped: A caught the error, B softened it to a 2.
Both labelers had the rubric's "factual errors = 1" rule available and each
still missed it on a different item — proof that raw agreement (55%) can look
reasonable while gold accuracy (40-50%) reveals real, rubric-following gaps
in both directions, not just one lazy labeler.

## How I'd scale this past 20 items

- Rubric as a living document, versioned against real edge cases
- Calibration before volume — annotators clear a gold-set threshold before labels count
- Continuous quality checks (gold items seeded invisibly into ongoing work)
- Adjudication workflow feeding back into the rubric
- Operational dashboard: κ, per-annotator accuracy, throughput, drift alerts

## Honest limitations

20 items and 2 labelers is a demonstration of the *machinery*, not a statistically stable study — κ is unstable at this N. Sample data is illustrative; the tool supports **Import** for real datasets.

---

*Built by Yadnaishwari Gaikwad as a hands-on study of the data-quality operations behind human-in-the-loop AI.*
