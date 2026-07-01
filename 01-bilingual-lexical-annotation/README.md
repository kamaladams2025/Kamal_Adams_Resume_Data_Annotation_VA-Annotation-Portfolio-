# Bilingual Lexical Annotation — Portuguese

## What this is
Three Portuguese frequency-list datasets (verbs, adjectives, prepositions) re-annotated with part-of-speech tags, morphological metadata, and ambiguity/confidence flags. See [`schema.md`](./schema.md) for full column definitions and tagging conventions.

## Why it matters
Raw frequency lists are common starting material in language-learning and NLP pipelines, but they're rarely annotation-ready — POS isn't always given, and source lists can contain real labeling errors. This sample demonstrates:
- Applying a consistent tagging schema across multiple related datasets
- Flagging genuine linguistic ambiguity rather than forcing a false single answer
- **Catching and documenting a labeling error in the source data** (see `portuguese-prepositions-tagged.csv` — 7 of 13 "preposition" entries were actually conjunctions or context-dependent words)
- Adding false-friend and idiomatic-usage notes relevant to translation QA (drawing on working proficiency in Spanish for contrastive analysis)

## Files
- `portuguese-verbs-tagged.csv` — 20 highest-frequency verbs, tagged with conjugation class and irregularity level
- `portuguese-adjectives-tagged.csv` — 16 highest-frequency adjectives, tagged with gender variation
- `portuguese-prepositions-tagged.csv` — 13-item source list, corrected and re-tagged after QA review
- `schema.md` — full tagging conventions and column definitions
