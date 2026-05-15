# Cover Letter Writer

## Purpose

Maintain a public, reusable cover-letter plugin and skill package. The repository should contain workflow logic, sanitized starter files, and setup documentation only.

## Project Shape

- `skills/cover-letter-writer/` - the bundled writer skill
- `.codex-plugin/plugin.json` - Codex plugin metadata
- `.claude-plugin/plugin.json` - Claude plugin metadata
- `my-applications/` - sanitized starter workspace with template files only
- `docs/` - setup and privacy documentation
- `examples-sanitized/` - sanitized examples only

The humanizer skill is not bundled here. For a separate polish pass, use the upstream skill from `https://github.com/blader/humanizer`.

## Privacy Rules

1. Never commit real user application material.
2. Keep files in `my-applications/` sanitized. Only `.template.md` starter files should be public.
3. Do not add one-person-specific assumptions to public instructions.
4. Replace personal facts with generic wording such as "the user's CV", "recommendation-backed evidence", or "prior examples".
5. Before publishing, scan for private names, employer names, exact personal history, real ads, generated letters, and copied recommendation text.

## Cover Letter Writing Rules

These rules should be preserved in the skill and documentation:

1. Never invent facts. Every claim must come from the user's CV, personal information, examples, recommendations, job ad, or current prompt.
2. Research the company before drafting unless the user explicitly says not to.
3. Research company values, culture, product or service, customer segment, and role context.
4. Map company signals to the user's source material before drafting.
5. Bring out only the strongest supported overlaps in the letter.
6. Write in the same language as the job ad unless the user asks otherwise.
7. Match tone and approximate length from prior examples when examples exist.
8. Use recommendation letters as background support only. Do not quote or directly mention them unless the user asks.
9. Do not over-emphasize leadership or management for specialist or individual-contributor roles unless the ad explicitly requires it.
10. Avoid em dashes, generic enthusiasm, inflated praise, formulaic transitions, and chatbot-style closers.

## Intended User Workflow

Users should work from `my-applications/` or a private workspace with the same layout:

- `cv/` - CV and personal information
- `recommendations/` - recommendation letters pasted into Markdown files
- `examples/` - prior cover letter examples, if available
- `ads/` - one Markdown file per job ad
- `output/raw/` - raw drafts
- `output/final/` - final drafts

Typical request:

```text
Write a cover letter for @ads/company-role.md
```

The writer should read the referenced ad first, then source material from sibling folders.

## Path Rules

Use generic workspace paths in public instructions:

- `cv/`
- `recommendations/`
- `examples/`
- `ads/`
- `output/raw/`
- `output/final/`

Do not hard-code private filenames such as a specific CV filename.

## Humanization

Always require a humanization pass before final output. Prefer the installed upstream `humanizer` skill when available:

```text
Use $humanizer to rewrite this draft without changing its facts.
```

If no humanizer skill is available, perform the pass manually and explicitly check for factual drift, em dashes, generic filler, and AI-sounding rhythm.
