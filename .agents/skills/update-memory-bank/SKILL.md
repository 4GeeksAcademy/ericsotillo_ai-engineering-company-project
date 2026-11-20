---
name: update-memory-bank
description: Update memory-bank/progress.md (and techContext.md on decisions or folder changes) after a task is completed, started or blocked. Not for projectbrief.md, BRIEFING.md, code or typo fixes.
---

# Update memory bank

Keep `memory-bank/` faithful to the real state of the repository after a task is completed, started or blocked.

## Inputs

- **Required:** what changed: a task completed, started or blocked.
- **Optional:** a technical decision (what, reason, date); a blocker found or resolved.
- **Read from the repository:** `git status --short` and `git diff --staged --name-only`, to check the change.

## Steps

1. Record `git status --short` before editing. Read `memory-bank/progress.md` and `memory-bank/techContext.md`.
2. If the developer did not say what changed, propose a summary from the git output and wait for confirmation. Edit nothing yet.
3. Check the reported change against the repository. If they contradict (for example, a "completed" file does not exist), stop and show the contradiction.
4. Update `progress.md`: move the task between *In progress*, *Next* and *Done*; add or remove rows in *Problems / blockers*; set *Last updated* to today (`YYYY-MM-DD`).
5. Update `techContext.md` only if:
   - a technical decision was reported: add it to *Architecture decisions* as `**Decision** · Reason · YYYY-MM-DD` with the developer's reason, and remove it from *To be decided*;
   - a folder in the *Application layer map* changed state.
6. Apply `.agents/rules/docs-style.md`.
7. Report each change in the chat with its evidence. Do not commit.

## Example

Input: "Finished the docs-style rule."

- `progress.md`: *Done* gains the rule with a link to `.agents/rules/docs-style.md`; *Next* loses "Rules in `.agents/rules/`"; *Last updated* is today.
- `techContext.md`: the `.agents/` row in the map changes from `not created` to `exists (rules/ only)`.

## Constraints

- Edit only `memory-bank/progress.md` and `memory-bank/techContext.md`.
- Never edit `projectbrief.md` or `projectbrief.es.md` (protected paths).
- Never invent a decision, a reason or a date other than today.
- Never commit: the pre-commit flow in `AGENTS.md` does.

## Acceptance criteria

- **AC-01** When the skill finishes, `memory-bank/progress.md` shall show today's date in "Last updated".
- **AC-02** The skill shall not modify any file other than `memory-bank/progress.md` and `memory-bank/techContext.md` (evidence: compare `git status --short` before and after the skill runs).
- **AC-03** When the developer reports a completed task, the task shall appear under *Done* and not under *In progress* or *Next*.
- **AC-04** If the developer does not say what changed, then the skill shall propose a summary from git and shall not modify any file until the developer confirms.
- **AC-05** If the reported change contradicts the repository, then the skill shall stop and show the contradiction without modifying any file.
- **AC-06** When the developer reports a technical decision, `techContext.md` shall record it with the developer's reason and no added reasons, and the item shall no longer appear under *To be decided*.
