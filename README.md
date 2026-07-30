# Annotation Quality Lab

`[https://<your-username>.github.io/annotation-quality-lab/annotation-quality-lab.html](https://yadnaishwari.github.io/Annotation-quality-lab/annotation-quality-lab.html)`


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

*[Fill in after running: κ, band, raw agreement, accuracy vs. gold, label distribution, disagreement count]*

## What the disagreements taught me

*[2–3 specific items and why they diverged — this is the most valuable section]*

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
