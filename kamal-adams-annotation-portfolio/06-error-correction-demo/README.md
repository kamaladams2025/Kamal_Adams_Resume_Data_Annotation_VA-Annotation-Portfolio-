# Error-Correction Demo — End-to-End QA Pass

## What this is
A small Spanish/English vocabulary dataset (15 rows) with **9 deliberately seeded errors** — covering the error categories most relevant to annotation QA work: mislabeling, duplicates, formatting inconsistency, scope inconsistency, and mistranslation. This is the clearest single demonstration of QA methodology in the portfolio, since the before/after/log structure makes the entire process auditable.

This dataset is intentionally synthetic and self-authored — unlike folders `01`–`03`, where the errors found were genuine issues in real source material, the errors here were planted on purpose specifically to demonstrate the QA workflow end to end.

## Error categories demonstrated
- **Mislabel** — a verb tagged as a noun
- **Duplicate row** — an exact repeat that would double-weight a frequency count
- **Formatting inconsistency** — inconsistent capitalization, trailing whitespace
- **Scope inconsistency** — one entry including an article ("el perro") where the convention across the dataset is bare headwords
- **Mistranslation / false-friend error** — "por qué" (why) glossed with the meaning of "porque" (because) — a classic confusion pair, and the kind of error that's easy to miss on a casual read but corrupts a dataset if it ships

## Files
- `dataset-with-errors.csv` — the flawed dataset, as it would arrive pre-QA
- `dataset-corrected.csv` — the same dataset post-QA
- `qa-log.csv` — every correction logged against the schema defined in [`../05-qa-error-log-template/`](../05-qa-error-log-template), with severity ratings and reviewer reasoning for each
