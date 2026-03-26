---
name: pr-comments-triage
description: Critically evaluate PR review comments against the actual code on the current branch. Use when the user triggers this skill on a branch and pastes PR review comments one at a time. Investigates each comment for validity rather than accepting it at face value, explains the verdict, and if valid asks before implementing the fix. Trigger phrases include "triage PR comments", "review comments", or when the user invokes this skill while on a feature branch.
license: MIT
metadata:
  author: Diego Petrucci
  version: "1.0"
---

# PR Comments Triage

Critically evaluate PR review comments pasted by the user. Do not assume comments are correct — investigate each one against the actual code.

## Workflow

### On trigger

1. Identify the current branch and its diff against the base branch (`git diff main...HEAD` or equivalent).
2. Ask the user to paste the first comment.

### For each comment

1. **Locate the relevant code** — find the file, function, or lines the comment refers to. Read the actual code on the branch.
2. **Investigate validity** — determine whether the comment is correct by reasoning about the code. Consider:
   - Is the concern factually accurate?
   - Does the suggestion improve correctness, readability, or performance?
   - Is it based on a misunderstanding of the code or its context?
   - Is it stylistic/subjective vs a real issue?
3. **Respond with a verdict:**

   **If valid:**
   - Explain *why* the comment is correct, referencing the specific code.
   - Describe the change needed.
   - Ask: "Want me to implement this fix?"
   - If the user agrees, make the change.

   **If not valid:**
   - Explain *why* the comment is incorrect or unnecessary, referencing the specific code.

4. **Ask for the next comment.**
