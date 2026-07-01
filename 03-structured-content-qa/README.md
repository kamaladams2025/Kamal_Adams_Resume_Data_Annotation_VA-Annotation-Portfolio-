# Structured Content QA — Quiz Dataset Validation

## What this is
A field-by-field validation pass on a Blooket-format quiz import sheet (10 ecology/environmental-science questions), checking every row against the platform's own stated import specification.

## Why it matters
This is the closest sample in the portfolio to pure structured-dataset QA: checking format compliance (field counts, character limits, valid index ranges) at scale, the kind of work involved in validating any large annotated or labeled dataset before it ships.

## Validation criteria applied
Per the import template's own stated spec:
- Time limit must not exceed 300 seconds
- Correct-answer field must reference a valid answer index (only the answer number, not text)
- Each question must have at least 3 answers (4th optional)

Plus one criterion not stated in the spec but standard QA practice:
- **Thematic consistency check** — does each answer option actually relate to its question, or could it be leftover/misplaced data from another row?

## What the QA pass found
9 of 10 questions passed all checks cleanly. **Question 9** ("What are trees planted at the edge of a farm to reduce wind erosion called?") failed the thematic consistency check: its 4th answer option, "Emergent layers," is a forest-canopy term lifted verbatim from Question 4's correct answer — almost certainly a copy-paste error during sheet creation. It doesn't break the import (the correct answer is still index 1, so grading is unaffected), but it's a distractor that doesn't belong and would confuse anyone reviewing the question bank. Flagged with a specific fix recommendation rather than just marked "fail."

## Files
- `ecology-quiz-validated.csv` — full validation pass, all 10 questions, with pass/fail status per check and reasoning for the one flagged row
