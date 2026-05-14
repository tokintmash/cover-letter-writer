---
name: cover-letter-writer
description: Use when drafting a tailored cover letter for a specific job ad file, such as "Write a cover letter for @ads/company-role.md", using the active workspace's `cv/`, `recommendations/`, and optional `examples/` folders while enforcing fact-only writing, role-appropriate framing, company-aware tailoring, and concise human tone. For a separate humanization pass, use the installed `humanizer` skill from https://github.com/blader/humanizer when available.
---

# Cover Letter Writer

Draft cover letters from project-local source material while preserving the user's factual record and writing style.

## Project Detection

First identify the active project root. Prefer project-local instructions over this skill when they are stricter.

Look for source folders and files such as `cv/`, `examples/`, `recommendations/`, `ads/`, `output/`, `AGENTS.md`, and `CLAUDE.md`.

## Required Inputs

Use these inputs when available:

- The specific job ad file named by the user, usually under `ads/`
- The active workspace's CV and personal information files under `cv/`
- Prior cover letter examples under `examples/`, if the user has provided any
- Recommendation letters pasted into files under `recommendations/`
- Project-local instructions

If the job ad or CV source cannot be discovered, ask for the missing material before drafting. Examples and recommendations are optional.

## Hard Rules

1. Never invent facts.
2. Use only claims supported by the CV, prior examples, recommendation material, or the user's prompt.
3. Write in the same language as the job ad unless the user asks otherwise.
4. Match the user's prior examples for tone, density, and approximate length.
5. Tailor the letter to the role instead of reusing a generic structure.
6. For specialist or individual-contributor roles, do not over-emphasize leadership unless the ad explicitly asks for it.
7. Use optional CV sections only when they strengthen fit for this specific role.
8. Treat recommendation letters as silent corroboration. Do not quote them or mention them directly unless the user asks.
9. Avoid em dashes, inflated praise, empty enthusiasm, and generic AI-sounding transitions.

## Drafting Workflow

1. Read the ad file the user referenced.
2. Read project-local instructions and source material from `cv/`, `recommendations/`, and `examples/` when present.
3. Identify the ad's language, priorities, seniority, and required evidence.
4. Research the company if current context or the user request calls for company-specific alignment.
5. Select the strongest fact-backed overlaps between the role and the user's background.
6. Draft a raw version that is concrete, concise, and role-specific.
7. Save the raw draft when the active project uses `output/raw/`.
8. Humanize the draft directly or invoke the installed upstream `humanizer` skill for a separate polishing pass when it is available.
9. Save the final version when the active project uses `output/final/`.
10. Run a final compliance pass for unsupported claims, wrong language, over-selling, em dashes, and private data leaks.

## Output Standard

Produce a finished letter that feels grounded in a real application: direct, specific, role-aware, and consistent with the user's existing examples.

When saving files, use project conventions. If none exist, prefer `output/raw/{company}-{role}.md` and `output/final/{company}-{role}.md`.

## References

Read only the reference files needed for the task:

- `references/workflow.md` for the full drafting and review workflow
- `references/data-layout.md` for expected project folders and missing-source behavior
- `references/role-framing.md` for seniority, specialist, and leadership framing
- `references/company-research.md` for company research and subtle alignment
