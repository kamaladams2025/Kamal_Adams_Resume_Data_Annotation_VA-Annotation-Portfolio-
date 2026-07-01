# Mandarin POS Annotation — TOCFL Novice 1 Word List

## What this is
A QA pass over the official 華語八千詞表 (Huayu 8000-Word List) Novice 1 tier — re-validating the source's own part-of-speech tagging against ~140 vocabulary entries spanning 9 thematic domains (personal info, work, education, travel, shopping, dining, etc.).

## Why it matters
This sample is built against an **official external reference standard** (SC-TOP / TOCFL) rather than self-generated data, which is closer to how real annotation work is evaluated — against a style guide or ground truth someone else defined. The QA pass surfaces:
- Two entries where the source list left the POS field blank
- One mislabeled particle (沒有, correctly a stative-verb negation, not Ptc)
- Several genuinely dual-category words (好, 叫, 還是, 想) where context determines POS — flagged rather than forced into a single tag

## Files
- `novice1-vocab-pos-tagged.csv` — full re-tagged dataset with source vs. verified POS, confidence flags, and reasoning
- `schema.md` — column definitions and full QA findings summary
