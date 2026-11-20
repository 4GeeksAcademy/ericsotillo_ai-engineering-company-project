---
description: Writing conventions for project documentation (memory bank, AGENTS.md, rules, skills). Apply when creating or editing Markdown files.
globs: "**/*.md"
alwaysApply: false
---

# Documentation style

**Scope:** auto-attached when creating or editing Markdown files (`**/*.md`).
**Basis:** conventions applied across `memory-bank/` and `AGENTS.md`.

## Rules

1. **Status labels**: use these exact words, never synonyms: `Exists`, `Template suggestion`, `Inference`, `To be confirmed`, `To be decided`. Under `To be decided`, a candidate the developer proposes may be named as `Candidate: X`, without adding reasons the developer did not give.
2. **Single source**: write each fact in one place and link to it elsewhere. Current state (done, in progress, blockers) lives only in `memory-bank/progress.md`; do not write statements that will go stale in other files.
3. **Project voice**: write as the Nexova project team. Use "iteration" and "project requirement"; "Milestone N" only as an iteration label. Never mention a course, grading or students.
4. **References**: cite `BRIEFING.md` by section heading, never by line number.
5. **Acronyms**: define on first use in each file, except universal ones: AI, API, CV, PDF, URL.
6. **Tool neutrality**: never name specific AI coding tools or vendors in versioned files.
7. **Spelling**: British English, consistent with `BRIEFING.md`.

## Correct / Incorrect

- Correct: `Backend architecture: To be decided.` Incorrect: `Backend: TBD (probably FastAPI).`
- Correct: `(BRIEFING.md › Customer Support (outsourced service))`. Incorrect: `(BRIEFING.md, line 103)`.
- Correct: `Service Level Agreement (SLA)` on first use. Incorrect: `Portable Document Format (PDF)`.
