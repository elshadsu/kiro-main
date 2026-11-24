---
name: "draft-release-notes"
description: >
  Draft release notes for the app from merged PRs. Invoke with
  /draft-release-notes VERSION when you want to produce release notes.
---

# Draft Release Notes

## Steps

1. Use the GitHub MCP server to fetch all merged PRs from the
   `elshadsu/kiro-main` repository's `main` branch since the last
   release. If no previous release exists, fetch all merged PRs. Do not
   assume the PR list is empty without querying GitHub. If the GitHub
   MCP call fails, report the error.

2. Apply the `pr-label-format` skill to categorize each PR.

3. Delegate description cleanup to the `ticket-fetcher` subagent. Pass
   the PR numbers, titles, and descriptions as the task prompt. Receive
   the cleaned list.

4. Delegate categorization to the `categorizer` subagent. Pass
   `ticket-fetcher`'s output as the task prompt. Receive the sorted
   Markdown.

5. Group PRs into Features, Fixes, and Improvements.

6. Draft each entry as a single user-facing sentence. Do not invent
   details; use only what's in the PR title or description.

7. Before asking for approval, write the completed PR review to
   `review-history.md` using the four fields below. Create the file if
   it does not exist. Do not write the Release Notes draft into this
   file.

   Use this format:

   - Date: YEAR-MONTH-DAY
   - PR: PR-NUMBER and title
   - Top finding: short description
   - Severity: severity

8. Present the complete draft to the user with the version number from
   the invocation argument. Ask: "Review complete. Approve to publish,
   or reply with edits."

## Guardrail

Only publish to GitHub releases after receiving explicit approval.

## Rules

Before drafting the Features section, read `docs/product-glossary.md`.

If a PR title or description matches a term in the `Search term` column,
use the corresponding value from the `Release notes name` column in the
output instead of the original wording.
