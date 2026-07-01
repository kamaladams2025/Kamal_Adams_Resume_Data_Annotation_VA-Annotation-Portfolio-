# QA Error-Log Template

## What this is
A reusable schema for logging annotation errors and corrections across any dataset/project, with example rows showing the format in use.

## Why it matters
Annotation QA work typically isn't just "fix the error" — it's documenting *what* was wrong, *why*, how it was fixed, and whether it needs a second reviewer, so an error pattern across thousands of rows can be tracked and reported on. This template is the schema used across this portfolio's QA passes (see `01`, `02`, `03`, and especially `06`).

## Columns
| Column | Description |
|---|---|
| `log_id` | Sequential ID |
| `dataset_name` | Which dataset the error was found in |
| `row_reference` | Row/record identifier |
| `field` | Which column/field had the issue |
| `original_value` | What the data said before correction |
| `issue_type` | mislabel / missing_data / formatting / duplicate / out_of_spec / thematic_inconsistency |
| `corrected_value` | What it was changed to |
| `severity` | high / medium / low — impact on downstream use if uncorrected |
| `reviewer_note` | Reasoning |
| `status` | resolved / pending_review / escalated |

## Files
- `annotation-qa-log-template.csv` — blank-ready schema with illustrative example rows
