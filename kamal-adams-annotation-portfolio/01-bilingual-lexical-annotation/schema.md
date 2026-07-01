# Schema — Bilingual Lexical Annotation (Portuguese)

## Purpose
Re-tag raw Portuguese frequency-list data with part-of-speech labels, gender/conjugation metadata, and ambiguity flags — the kind of structured enrichment used in cross-lingual annotation and translation-QA pipelines.

## Source
Raw word/translation pairs generated as Portuguese self-study reference material (verbs, adjectives, prepositions — top frequency items). Source lists were unlabeled beyond the word and its English gloss.

## Columns

### `portuguese-verbs-tagged.csv`
| Column | Description |
|---|---|
| `portuguese` | Headword |
| `english` | Gloss |
| `frequency_rank` | Rank within this set |
| `pos_tag` | Part of speech (V = verb) |
| `conjugation_class` | regular / irregular |
| `irregularity_flag` | high / medium / low — degree of conjugation unpredictability a learner or annotator should expect |
| `notes` | False-friend risks, idiomatic uses, semantic range, common confusions |

### `portuguese-adjectives-tagged.csv`
| Column | Description |
|---|---|
| `gender_variation` | Masculine/feminine forms, or "invariable" if the adjective doesn't change |
| `confidence_flag` | Annotation confidence — low flags cases where meaning shifts by sentence position |

### `portuguese-prepositions-tagged.csv`
| Column | Description |
|---|---|
| `pos_tag` | Corrected part-of-speech (see QA note below) |
| `confidence_flag` | low = genuinely ambiguous and context-dependent; high = unambiguous |

## QA note — source list mislabeling caught during annotation
The original "prepositions" source list included seven words (`e`, `mas`, `ou`, `que`, `se`, `como`, `porque`) that are **not** prepositions — they're coordinating/subordinating conjunctions, relative pronouns, or context-dependent multi-category words. Only 6 of the 13 entries are unambiguous true prepositions.

This is flagged explicitly in `portuguese-prepositions-tagged.csv` rather than silently corrected, because surfacing the original labeling error — and showing the reasoning for the correction — is the actual annotation/QA skill being demonstrated here, not just producing a clean final list.

## Confidence flag convention
- **high** — single, unambiguous POS regardless of context
- **medium** — generally one POS, but with a notable idiomatic or position-dependent exception
- **low** — POS genuinely depends on sentence-level context; would require a human reviewer or disambiguation model in a real pipeline
