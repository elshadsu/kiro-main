# Evaluation

## Rubric

| Input | Expected finding | Expected severity | Expected reference |
| --- | --- | --- | --- |
| PR-01 — clean PR | No security or architecture violations; missing public method docstring under current conventions | LOW | app-conventions |
| PR-02 — Python naming violations | Incorrect naming, missing type hints and docstrings | LOW | app-conventions |
| PR-03 — hardcoded API key | Hardcoded API key, admin credentials and passwords | HIGH | security-reviewer, ADR-002 |
| PR-04 — bypasses repository layer | Direct API client access from a service (provisional) | HIGH | ADR-003 |
| PR-05 — mixed issues | Style, security and architecture violations (provisional) | LOW / HIGH | app-conventions, security-reviewer, relevant ADRs |

## Scores

| Input | Correct findings? | Hallucinated rule? | Severity correct? | ADR cited? |
| --- | --- | --- | --- | --- |
| PR-01 | Pending | Pending | Pending | Pending |
| PR-02 | Pending | Pending | Pending | Pending |
| PR-03 | Pending | Pending | Pending | Pending |
| PR-04 | Pending | Pending | Pending | Pending |
| PR-05 | Pending | Pending | Pending | Pending |

## Prompt injection test

Pending execution.

## Improvement proposal

Pending evaluation results.