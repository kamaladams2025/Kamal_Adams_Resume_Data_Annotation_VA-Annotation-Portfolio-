# Schema — Mandarin POS Annotation (TOCFL Novice 1)

## Purpose
Re-validate and lightly correct an official TOCFL (Test of Chinese as a Foreign Language) 8000-word frequency list — Novice 1 tier — against its own stated part-of-speech tagging, flagging inconsistencies and dual-category words.

## Source
華語八千詞表 (Huayu 8000-Word List), Novice 1 tier — Steering Committee for the Test of Proficiency-Huayu (SC-TOP), the official government-affiliated Mandarin proficiency standard used in Taiwan. Source data includes context domain, vocabulary, pinyin, and a part-of-speech (POS) field.

## Columns
| Column | Description |
|---|---|
| `context_domain` | Thematic category as assigned by the source list (個人資料 = personal info, 教育 = education, etc.) |
| `vocabulary` | Headword, including accepted character variants |
| `pinyin` | Romanization as given in source |
| `pos_source` | POS tag exactly as it appears in the original list |
| `pos_verified` | POS tag after QA review — identical to source unless a discrepancy is noted |
| `confidence_flag` | high / medium / low |
| `notes` | Reasoning for any reclassification, dual-category usage, or learner pitfalls |

## QA findings from this review
1. **Two entries had blank POS fields in the source** (對不起 "sorry," 請問 "may I ask") — both fixed expressions that don't fit the list's core noun/verb schema cleanly. Classified here as Inj (interjection) and V respectively, with reasoning noted.
2. **Numerals (一–十, 百, 千, etc.) are tagged N in the source** rather than as a distinct numeral class. Retained as N where the source convention is internally consistent, but flagged medium-confidence since most computational POS schemes (and TOCFL's own higher-tier lists) separate numerals from general nouns.
3. **沒有 (méiyǒu) is tagged Ptc (particle) in the source**, but functions as the negated form of 有 (Vst, "to have/there is") — reclassified with reasoning noted, since tagging it as a particle would misrepresent its syntactic role.
4. **好 (hǎo) is tagged Adv only**, but is a stative verb (Vs, "good") in the large majority of its uses, with adverbial/intensifier use ("好漂亮," so pretty) being the secondary function. Flagged low-confidence/dual-category rather than silently overridden.

## Confidence flag convention
Same convention as the Portuguese annotation set (see `../01-bilingual-lexical-annotation/schema.md`) — high/medium/low based on how context-dependent the POS assignment is.
